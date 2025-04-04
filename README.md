[ERROR] Error while parsing schema(s).Location [ file:/C:/Users/kpuchagk/workspace/pltformupgrade/release/drugmdm-loadarticleupdate/schema/src/main/resources/schema/xsd/ArticleUpdate.xsd{5,62}].
org.xml.sax.SAXParseException: Unsupported binding namespace "http://annox.dev.java.net". Perhaps you meant "http://java.sun.com/xml/ns/jaxb/xjc"?


<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>com.walgreens.pharmacy.starter</groupId>
		<artifactId>rxp-spring-boot-starters-bom</artifactId>
		<version>2.0.4-RELEASE</version>
	</parent>

	<groupId>com.walgreens.pharmacy</groupId>
	<artifactId>drugmdm-loadarticleupdate-parent</artifactId>
	<version>1.0.0-SNAPSHOT</version>
	<packaging>pom</packaging>
	<name>Drug MDM - Load Article Update - ${project.version}</name>
	<description>Minion to consume Kafka event stream (IntegrationSAPArticleUpdateRequest) provided by Minions (product-loadproduct, product-loadpag) and read data from cassandra database to produce SAP article updates. Uses: drugmdm-product-data, drugmdm-pag-data</description>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>17</java.version>
	</properties>
	<modules>
		<module>gateway</module>
		<module>schema</module>
	</modules>
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>io.fabric8</groupId>
				<artifactId>kubernetes-client</artifactId>
				<version>6.7.2</version>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>

	<dependencies>
		<dependency>
			<groupId>io.fabric8</groupId>
			<artifactId>kubernetes-model</artifactId>
			<version>6.7.2</version>
		</dependency>
		<dependency>
			<groupId>io.fabric8</groupId>
			<artifactId>kubernetes-model-common</artifactId>
			<version>6.7.2</version>
		</dependency>
		<dependency>
			<groupId>io.fabric8</groupId>
			<artifactId>kubernetes-model-core</artifactId>
			<version>6.7.2</version>
		</dependency>
	</dependencies>
	<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-assembly-plugin</artifactId>
				<configuration>
					<skipAssembly>true</skipAssembly>
				</configuration>
			</plugin>
		</plugins>
	</build>
</project>
