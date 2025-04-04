=========
<properties>
    <java.version>17</java.version>
    <maven.compiler.source>17</maven.compiler.source>
    <maven.compiler.target>17</maven.compiler.target>
</properties>

<dependencies>
    <dependency>
        <groupId>jakarta.xml.bind</groupId>
        <artifactId>jakarta.xml.bind-api</artifactId>
        <version>4.0.0</version>
    </dependency>
    <dependency>
        <groupId>com.sun.xml.bind</groupId>
        <artifactId>jaxb-impl</artifactId>
        <version>4.0.3</version>
        <scope>runtime</scope>
    </dependency>
    <dependency>
        <groupId>org.jvnet.jaxb2_commons</groupId>
        <artifactId>jaxb2-namespace-prefix</artifactId>
        <version>1.3</version>
    </dependency>
</dependencies>

<build>
    <plugins>
        <plugin>
            <groupId>org.jvnet.jaxb2.maven2</groupId>
            <artifactId>maven-jaxb2-plugin</artifactId>
            <version>0.15.3</version>
            <executions>
                <execution>
                    <id>articlemaster</id>
                    <goals>
                        <goal>generate</goal>
                    </goals>
                    <configuration>
                        <schemas>
                            <schema>
                                <fileset>
                                    <directory>${dependency-unpack-dir}/schema/xsd</directory>
                                    <includes>
                                        <include>*.xsd</include>
                                    </includes>
                                </fileset>
                            </schema>
                        </schemas>
                        <generateDirectory>${generated-sources-dir}/xjc-articlemaster/src/gen/java</generateDirectory>
                        <bindingDirectory>${dependency-unpack-dir}/schema/xjb</bindingDirectory>
                        <bindingIncludes>
                            <include>ArticleMaster.xjb</include>
                        </bindingIncludes>
                        <extension>true</extension>
                        <args>
                            <arg>-Xnamespace-prefix</arg>
                        </args>
                        <plugins>
                            <plugin>
                                <groupId>org.jvnet.jaxb2_commons</groupId>
                                <artifactId>jaxb2-namespace-prefix</artifactId>
                                <version>1.3</version>
                            </plugin>
                        </plugins>
                        <episodeFile>${project.build.directory}/generated-sources/xjc/META-INF/jaxb-articlemaster.episode</episodeFile>
                    </configuration>
                </execution>
            </executions>
            <dependencies>
                <dependency>
                    <groupId>org.glassfish.jaxb</groupId>
                    <artifactId>jaxb-runtime</artifactId>
                    <version>4.0.3</version>
                </dependency>
            </dependencies>
        </plugin>
    </plugins>
</build> 
=========




// ... existing code ...
<plugin>
    <groupId>org.jvnet.jaxb2.maven2</groupId>
    <artifactId>maven-jaxb2-plugin</artifactId>
    <version>0.15.3</version>
    <executions>
        <execution>
            <id>articlemaster</id>
            <goals>
                <goal>generate</goal>
            </goals>
            <configuration>
                <schemas>
                    <schema>
                        <fileset>
                            <directory>${dependency-unpack-dir}/schema/xsd</directory>
                            <includes>
                                <include>*.xsd</include>
                            </includes>
                        </fileset>
                    </schema>
                </schemas>
                <generateDirectory>${generated-sources-dir}/xjc-articlemaster/src/gen/java</generateDirectory>
                <bindingDirectory>${dependency-unpack-dir}/schema/xjb</bindingDirectory>
                <bindingIncludes>
                    <include>ArticleMaster.xjb</include>
                </bindingIncludes>
                <!-- Add these new configuration elements -->
                <args>
                    <arg>-extension</arg>
                    <arg>-Xnamespace-prefix</arg>
                </args>
                <plugins>
                    <plugin>
                        <groupId>org.jvnet.jaxb2_commons</groupId>
                        <artifactId>jaxb2-namespace-prefix</artifactId>
                        <version>1.3</version>
                    </plugin>
                </plugins>
            </configuration>
        </execution>
    </executions>
</plugin>
// ... existing code ...



<dependency>
    <groupId>org.jvnet.jaxb2_commons</groupId>
    <artifactId>jaxb2-namespace-prefix</artifactId>
    <version>1.3</version>
</dependency>
<properties>
    <java.version>17</java.version>
    <maven.compiler.source>17</maven.compiler.source>
    <maven.compiler.target>17</maven.compiler.target>
</properties>

[INFO] Sources are not up-to-date, XJC will be executed.
[ERROR] Error while parsing schema(s).Location [ file:/C:/Users/kpuchagk/workspace/pltformupgrade/release/drugmdm-loadarticlemaster/target/dependency/schema/xsd/ArticleMaster.xsd{4,66}].
org.xml.sax.SAXParseException: Unsupported binding namespace "http://jaxb2-commons.dev.java.net/namespace-prefix". Perhaps you meant "http://jaxb.dev.java.net/plugin/code-injector"?
    at com.sun.tools.xjc.reader.AbstractExtensionBindingChecker.error (AbstractExtensionBindingChecker.java:183)
