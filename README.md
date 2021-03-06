# Liferay Faces Generator

The Liferay Faces Generator is a code generator designed to generate
Java Server&trade; Faces (JSF) custom components and `taglib.xml` files. The
aim of the generator is to reduce the errors and duplicated work associated
with writing JSF custom components. The generator takes as input a single
[`taglib.xml`-like](https://github.com/stiemannkj1/liferay-faces-generator/blob/master/src/main/resources/common-tags.xml)
file and outputs custom components and a `taglib.xml` file.

## License

[GNU Lesser General Public License (LGPL), Version
2.1](http://www.gnu.org/licenses/old-licenses/lgpl-2.1.txt)

## Building From Source

Using [Maven](https://maven.apache.org/) 3.x:

	mvn clean install

## Usage

The generator can be used from the command-line like so:

	liferay-faces-generator.jar new-tags.xml

The generator can also be used with `maven` via the `exec-maven-plugin`:

```
<plugin>
	<groupId>org.codehaus.mojo</groupId>
	<artifactId>exec-maven-plugin</artifactId>
	<version>1.2.1</version>
	<executions>
		<execution>
			<goals>
				<goal>java</goal>
			</goals>
			<phase>generate-sources</phase>
			<configuration>
				<includeProjectDependencies>false</includeProjectDependencies>
				<includePluginDependencies>true</includePluginDependencies>
				<mainClass>com.liferay.faces.generator.Generator</mainClass>
				<arguments>
					<argument>new-tags.xml</argument>
				</arguments>
				<executableDependency>
					<groupId>com.liferay.faces.generator</groupId>
					<artifactId>liferay-faces-generator</artifactId>
				</executableDependency>
			</configuration>
		</execution>
	</executions>
	<dependencies>
		<dependency>
			<groupId>com.liferay.faces.generator</groupId>
			<artifactId>liferay-faces-generator</artifactId>
			<version>1.0-SNAPSHOT</version>
		</dependency>
	</dependencies>
</plugin>
```

## Community Participation

Please post questions in the [Liferay Faces
Forum](http://www.liferay.com/community/forums/-/message_boards/category/13289027).
Defects and feature requests can be posted in the [Liferay Faces Issue
Tracker](http://issues.liferay.com/browse/FACES).
