FROM alpine/git
WORKDIR /app
RUN git clone https://github.com/hutaojiazi/store-demo.git

FROM gradle:7.5.0-jdk17
WORKDIR /app
COPY --from=0 /app/store-demo /app
RUN gradle clean assemble

FROM openjdk:17.0.1-jdk-slim
WORKDIR /app
COPY --from=1 /app/build/libs/*.jar /app

# Uncomment the RUN line if the version has changed
# Then use the output of docker build to modify the
# .jar file name
#RUN ls

CMD ["java","-jar","demo-0.0.1-SNAPSHOT.jar"]
