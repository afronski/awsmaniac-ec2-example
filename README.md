# Amazon EC2 example for [AWS Maniac live stream](https://awsmaniac.com/live)

## What is it?

It is an example that I have prepared for the live stream from *AWS Certification* support group for *Associate level* preparations done as a part of [AWS Maniac](https://awsmaniac.com) initiative.

## Prerequisites

- *MySQL* (`>= 8.0`), locally you can use *Docker* for that:
    - `docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=localInstance2020 -p 3306:3306 -d mysql:8`

## Examples

```bash
# Login:
curl -i -XPOST -H "Content-Type: application/x-www-form-urlencoded"        \
     -d "username=admin@example.com&password=12345" http://localhost/login

# List all notes:
curl -i -H "Cookie: JSESSIONID=...; Path=/; HttpOnly" http://localhost/notes

# Create a note:
curl -i -XPUT -H "Cookie: JSESSIONID=...; Path=/; HttpOnly" -H "Content-Type: application/json"    \
     -d '{"title": "1st note", "message": "message", "location": "Poland"}' http://localhost/notes
```

## Environment variables for a deployment

- `SERVER_PORT`: `5000`
- `SPRING_DATASOURCE_URL`: `jdbc:mysql://${RDS_HOSTNAME}:${RDS_PORT}/${RDS_DB_NAME}`
- `SPRING_DATASOURCE_USERNAME`: `${RDS_USERNAME}`
- `SPRING_DATASOURCE_PASSWORD`: `${RDS_PASSWORD}`
- `SPRING_JPA_DATABASE_PLATFORM`: `org.hibernate.dialect.MySQL8Dialect`
- `SPRING_JPA_HIBERNATE_DDL_AUTO`: `update`

## License

- [MIT](LICENSE.md)

## Authors

- [Wojciech Gawroński (afronski) - AWS Maniac](https://github.com/afronski)
