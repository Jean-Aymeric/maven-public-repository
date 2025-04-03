# maven-public-repository

# Made with ❤️ by [JAD](mailto:jeanaymeric@gmail.com)

Public repository for maven packages shared with my students

To add this repository to your maven project, add the following lines to your `pom.xml`:

```xml

<repositories>
    <repository>
        <id>jad-maven-public-repository</id>
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

# Configuring Maven to Access a GitHub Repository

This guide explains how to configure Maven to access a GitHub Packages repository, for both cases: when the
`settings.xml` file does not exist and when it already exists.

---

## Case 1: `settings.xml` File Does Not Exist

If the `settings.xml` file is not present, follow these steps:

1. **Create the `.m2` Directory and `settings.xml` File**:
    - On Linux/Mac: Create the file at `~/.m2/settings.xml`.
    - On Windows: Create the file at `%USERPROFILE%\.m2\settings.xml`.

2. **Add the Repository Configuration**:
   Add the following content to the new `settings.xml` file:
   ```xml
   <settings>
       <servers>
           <server>
               <id>jad-maven-public-repository</id>
               <username>Jean-Aymeric</username>
               <password>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</password>
           </server>
       </servers>
   </settings>

## Case 2: `settings.xml` File Exists

If the `settings.xml` file already exists, you just need to add the server configuration for your GitHub repository
without overwriting existing settings.

1. **Open the Existing `settings.xml` File**:
   Locate the file at:
    - `~/.m2/settings.xml` (Linux/Mac)
    - `%USERPROFILE%\.m2\settings.xml` (Windows)

2. **Add the GitHub Repository Configuration**:
   Locate the `<servers>` section in the file. If it doesn't exist, add it. Then include this block:
   ```xml
   <server>
       <id>jad-maven-public-repository</id>
       <username>Jean-Aymeric</username>
       <password>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</password>
   </server>
