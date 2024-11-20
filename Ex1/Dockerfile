FROM openjdk:11-jdk-slim

WORKDIR /app

COPY src /app/src

RUN javac src/TestJava.java

CMD ["java", "-cp", "/app/src", "TestJava"]