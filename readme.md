# Maven archetype for Spring Utility Project
This is sample project for Maven Archetype: Spring Utility Project Template

## Setup

Clone:
	
	git clone https://github.com/psladecek/maven-achetypes.git
	cd maven-achetypes

Build and install archetype into local repository 
	
	mvn clean install
	
You will get local repository at path:	
	
	C:\Users\xxx\.m2\repository\maven-archetypes  
where xxx is your login name

## Usage

Run command:

	mvn archetype:generate -DgroupId=maven-archetypes -Dversion=1.0 -DarchetypeCatalog=local -DartifactId=utility -Dpackage=com.foo.bar

after that you will get

	[INFO] Scanning for projects...
	[INFO]
	[INFO] ------------------------------------------------------------------------
	[INFO] Building Maven Archetype for Spring Utility Project Template 1.0
	[INFO] ------------------------------------------------------------------------
	[INFO]
	[INFO] >>> maven-archetype-plugin:2.0:generate (default-cli) @ spring-utility-project >>>
	[INFO]
	[INFO] <<< maven-archetype-plugin:2.0:generate (default-cli) @ spring-utility-project <<<
	[INFO]
	[INFO] --- maven-archetype-plugin:2.0:generate (default-cli) @ spring-utility-project ---
	[INFO] Generating project in Interactive mode
	[INFO] No archetype defined. Using maven-archetype-quickstart (org.apache.maven.archetypes:maven-archetype-quickstart:1.0)
	Choose archetype:
	1: local -> maven-archetypes:spring-utility-project (Maven Archetype for Spring Utility Project Template)
	Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): :

choose number 1

	Choose archetype:
	1: local -> maven-archetypes:spring-utility-project (Maven Archetype for Spring Utility Project Template)
	Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): : 1
	[INFO] Using property: groupId = maven-archetypes
	INFO] Using property: artifactId = utility
	[INFO] Using property: version = 1.0
	[INFO] Using property: package = com.foo.bar
	Confirm properties configuration:
	groupId: maven-archetypes
	artifactId: utility
	version: 1.0
	package: com.foo.bar
 	Y: :
choose y

	Confirm properties configuration:
	groupId: maven-archetypes
	artifactId: utility
	version: 1.0
	package: com.foo.bar
 	Y: : y
	[INFO] ----------------------------------------------------------------------------
	[INFO] Using following parameters for creating project from Archetype: spring-utility-project:1.0
	[INFO] ----------------------------------------------------------------------------
	[INFO] Parameter: groupId, Value: maven-archetypes
	[INFO] Parameter: artifactId, Value: utility
	[INFO] Parameter: version, Value: 1.0
	[INFO] Parameter: package, Value: com.foo.bar
	[INFO] Parameter: packageInPathFormat, Value: com/foo/bar
	[INFO] Parameter: package, Value: com.foo.bar
	[INFO] Parameter: version, Value: 1.0
	[INFO] Parameter: groupId, Value: maven-archetypes
	[INFO] Parameter: artifactId, Value: utility
	[INFO] Parent element not overwritten in c:\dev\sts-workspace\SpringDemos\maven-archetypes\utility\pom.xml
	[INFO] project created from Archetype in dir: c:\dev\sts-workspace\SpringDemos\maven-archetypes\utility
	[INFO] ------------------------------------------------------------------------
	[INFO] Reactor Summary:
	[INFO]
	[INFO] Maven Archetype for Spring Utility Project Template  SKIPPED
	[INFO] Maven Archetype ................................... SUCCESS [1.742s]
	[INFO] ------------------------------------------------------------------------
	[INFO] BUILD SUCCESS
	[INFO] ------------------------------------------------------------------------
	[INFO] Total time: 2.101s
	[INFO] Finished at: Mon Jul 08 11:26:08 CEST 2013
	[INFO] Final Memory: 9M/22M
	[INFO] ------------------------------------------------------------------------

<b>You can parametrize the following:</b>
	
Project name

	-DartifactId=utility

Top-level packaging

	-Dpackage=com.foo.bar
		
Results:
	
	.
	|____pom.xml
	|____src
	| |____main
	| | |____java
	| | | |____com
	| | | |____foo
	| | | | |____bar
	| | | | | | |____ExampleService.java
	| | | | | | |____Service.java
	| | |____resources
	| | | |____META-INF
	| | | | |____spring
	| | | | | |____app-context.xml
	| |____site
	| | |____site.xml
	| |____test
	| | |____java
	| | | |____com
	| | | | |____foo
	| | | | | |____bar
	| | | | | | |____ExampleConfigurationTests.java
	| | | | | | |____ExampleServiceTests.java
	| | |____resources
	| | | |____com
	| | | | |____foo
	| | | | | |____bar
	| | | | | | |____ExampleConfigurationTests-context.xml
	| | | |____log4j.properties	

Basically it is the same as structure created by STS Wizard - Simple Spring Utility Project

	Spring Tool Suite 
	Version: 3.2.0.RELEASE
	Build Id: 201303060821

## Converting to Eclipse project

Go to the project name

	cd utility

generate .project and .classpath

	mvn eclipse:eclipse

fix .classpath with this command

	sed -i '/kind=\"var\"/d' ".classpath"

after that you can import created utility project to STS.
