# Public Docker Images

A collection of images that i use
on a regular basis.

## Images

| Image                                               | Purpose                                                   |
|-----------------------------------------------------|-----------------------------------------------------------|
| `maaxgr/bootstrap-email:1.4.0`                      | Version 1.4.0 of bootstrap-email ruby gem.                |
| `maaxgr/bootstrap-email-jdk:openjdk-11_bmail-1.4.0` | Version 1.4.0 of bootstrap-email ruby gem and openjdk 11. |

## Usage

All images are available on [Docker Hub](https://hub.docker.com/u/maaxgr),
so you can just use them as base image in your `Dockerfile`.

```dockerfile
FROM maaxgr/bootstrap-email-jdk:openjdk-11_bmail-1.4.0

# add jar
WORKDIR /jars
ADD build/libs/test.jar .

WORKDIR /run
CMD ["java", "-jar", "/jars/test.jar"]
```