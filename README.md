# maven-public-repository

# Made with ❤️ by [JAD](mailto:jeanaymeric@gmail.com)

---

Public repository for maven packages shared with my students

---

# How to use the repository

## Create a GitHub Personal Access Token for Maven Repository Access

---

1. **Log In to Your GitHub Account**:
    - Go to [https://github.com](https://github.com) and log in with your credentials.

2. **Navigate to Personal Access Token Settings**:
    - Click on your profile picture in the top-right corner.
    - Select **Settings** from the dropdown menu.
    - In the left sidebar, scroll down and click on **Developer settings**.
    - Select **Personal access tokens** and then click on **Tokens (classic)**.

3. **Generate a New Token**:
    - Click on the **Generate new token (classic)** button.

4. **Set Up the Token Details**:
    - **Token Name**: Enter `jad-maven-public-repository` as the name for the token.
    - **Expiration**: Choose an expiration date. For example, 90 days is a good option, but you can select no expiration
      if you prefer.
    - **Permissions**: Scroll down to **Select scopes** and check the following:
        - `read:packages` - Required for accessing GitHub Packages.
    - Leave other scopes unchecked.

5. **Generate the Token**:
    - Click the **Generate token** button at the bottom of the page.

6. **Save the Token**:
    - Once the token is generated, **copy it immediately**. You will not be able to see it again after leaving the page.
    - Save the token securely, for example in a password manager or a safe file.

---

## Use the Token

**Add the Token to Maven Settings**:

- Open or create the file `settings.xml` located in:
- `~/.m2/settings.xml` (Linux/Mac).
- `%USERPROFILE%\.m2\settings.xml` (Windows).
- Add the following entry inside the `<servers>` section:

```xml

<servers>
    <server>
        <id>maven-public-repository</id>
        <username>[Your GitHub Username]</username>
        <password>[Your Token]</password>
    </server>
</servers>
```

- Replace `[Your GitHub Username]` with your GitHub username.
- Replace `[Your Token]` with the token you just created.

---

## How to Use the Maven Repository

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

---

By following these steps, you’ll be able to create and use a GitHub token to access the Maven repository
`jad-maven-public-repository` successfully.

---

## Important Notes

- **Keep Your Token Secure**:
    - Never share your token publicly or upload it to public repositories like GitHub. If it gets exposed, GitHub will
      automatically revoke the token.

- **Token Expiration**:
    - When the token expires, you’ll need to generate a new one and update it in your `settings.xml`.

- **Troubleshooting**:
    - If Maven fails to authenticate or returns a 401 error, double-check that:
        - The token has the `read:packages` scope enabled.
        - Your GitHub username and token are correctly added to the `settings.xml` file.
