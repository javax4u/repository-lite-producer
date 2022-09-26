```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>virtualdoxx</groupId>
    <artifactId>producer</artifactId>
    <version>0.0</version>
    <packaging>jar</packaging>
    <dependencies>

    </dependencies>
    <build>
        <pluginManagement>
            <plugins>

                <plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-plugin-plugin</artifactId>
                    <version>3.6.0</version>
                    <configuration>
                        <!-- see http://jira.codehaus.org/browse/MNG-5346 -->
                        <skipErrorNoDescriptorsFound>true</skipErrorNoDescriptorsFound>
                    </configuration>
                </plugin>
                <plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-site-plugin</artifactId>
                    <version>3.9.1</version>
                </plugin>
            </plugins>
        </pluginManagement>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>8</source>
                    <target>8</target>
                </configuration>
            </plugin>

            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-release-plugin</artifactId>
                <version>3.0.0-M1</version>
            </plugin>
        </plugins>
    </build>
    <distributionManagement>
        <repository>
            <id>my-domain-repository</id>
            <url>http://www6c.virtualdoxx.com:8082/releases</url>
        </repository>
    </distributionManagement>
</project>
```

## settings.xml

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">
        <servers>
            <server>
                <!-- Id has to match the id provided in pom.xml -->
                <id>my-domain-repository</id>
                <username>vdoxx</username>
                <password>vdoxx999</password>
            </server>
        </servers>
</settings>
```

### successful output
```shell
[INFO] 
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ producer ---
[INFO] Building jar: /Users/rupeshkumar/repository-lite-producer/target/producer-0.0.jar
[INFO] 
[INFO] --- maven-install-plugin:2.4:install (default-install) @ producer ---
[INFO] Installing /Users/rupeshkumar/repository-lite-producer/target/producer-0.0.jar to /Users/rupeshkumar/.m2/repository/virtualdoxx/producer/0.0/producer-0.0.jar
[INFO] Installing /Users/rupeshkumar/repository-lite-producer/pom.xml to /Users/rupeshkumar/.m2/repository/virtualdoxx/producer/0.0/producer-0.0.pom
[INFO] 
[INFO] --- maven-deploy-plugin:2.7:deploy (default-deploy) @ producer ---
Uploading to my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/0.0/producer-0.0.jar
Uploaded to my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/0.0/producer-0.0.jar (2.4 kB at 1.3 kB/s)
Uploading to my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/0.0/producer-0.0.pom
Uploaded to my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/0.0/producer-0.0.pom (2.1 kB at 1.5 kB/s)
Downloading from my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/maven-metadata.xml
Uploading to my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/maven-metadata.xml
Uploaded to my-domain-repository: http://www6c.virtualdoxx.com:8082/releases/virtualdoxx/producer/maven-metadata.xml (295 B at 218 B/s)
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  7.135 s
[INFO] Finished at: 2022-09-26T11:12:46+05:30
[INFO] ------------------------------------------------------------------------
rupeshkumar@ENCOPDBANLT0254 repository-lite-producer % 
```