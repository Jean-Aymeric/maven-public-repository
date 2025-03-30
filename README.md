# maven-public-repository
# Made with ❤️ by [JAD](mailto:jeanaymeric@gmail.com)
Public repository for maven packages shared with my students

To add this repository to your maven project, add the following lines to your `pom.xml`:

```xml

<repositories>
    <repository>
        <id>maven-public-repository</id>
        <url>https://maven.pkg.github.com/Jean-Aymeric/maven-public-repository</url>
    </repository>
</repositories>
```

After that, you can add the dependencies you need in the `dependencies` section of your `pom.xml` file. For example:

```xml

<dependency>
    <groupId>com.jad</groupId>
    <artifactId>textwindow</artifactId>
    <version>1.0.0</version>
</dependency>
```
