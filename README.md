# spring-boot-openapi
spring-boot-openapi

This is url for swagger api
https://localhost:9091/swagger-ui.html

https://localhost:9091/v3/api-docs

		<dependency>
			<groupId>org.springdoc</groupId>
			<artifactId>springdoc-openapi-ui</artifactId>
			<version>1.5.5</version>
		</dependency>

Below annotation is required

    @OpenAPIDefinition(info = @Info(title = "Sing boot OpenAPi application", description = "This is an rest api ui for understanding",
    termsOfService = "nothing", license = @License(name = "openapi"), contact = @Contact(email = "sample@test.com"), version = "1.0.0"))

Docker commands

    docker build -t dockerimage .
    docker run -d -p 80:8080 dockerimage
    docker container ps
    docker logs containerid -f
    docker exec -it containerid sh
    docker login
    docker push test/dockerimage:0.0.1

Use below plugins for Maven plugins for docker image

          <plugins>
                <plugin>
                    <groupId>com.spotify</groupId>
                    <artifactId>dockerfile-maven-plugin</artifactId>
                    <version>1.4.0</version>
                    <configuration>
                        <repository>abhi020290/${project.artifactId}</repository>
                        <tag>${project.version}</tag>
                        <buildArgs>
                            <JAR_FILE>target/${project.build.finalName}.jar</JAR_FILE>
                        </buildArgs>
                    </configuration>
                    <executions>
                        <execution>
                            <id>default</id>
                            <phase>install</phase>
                            <goals>
                                <goal>build</goal>
                                <goal>push</goal>
                            </goals>
                        </execution>
                    </executions>
                </plugin>
         <plugins>
         <finalName>bizdata-batch-processor</finalName>



    
