# Main Project Repository dedicated for repo usage

This repo is dedicated to the declaration of project structure for the google repo tool

## Start a project

To start developping a projet please follow this procedure:

1. Install the [repo tool](https://source.android.com/setup/develop#installing-repo)
2. On your file system create a repository for your project
3. configure your user

    ```bash
        git config --global user.name Your Name
        git config --global user.email you@example.com
    ```

4. Initialize your repo (for example the infracost project (branch infracost))

    ```bash
        repo init -u https://github.com/matthieupetite/projects.git -b infracost
    ```

5. Sync your sources

    ```bash
        repo sync 
    ```

    or to speed it up

    ```bash
        repo sync -c -j8 
    ```

## Create a project

To create a new project please follow the procedure

1. Create a branch in the project repo
2. Edit the default.xml file to define your configuration

Here is the manifest of a sample project

```xml
<manifest>
    <remote name="github" fetch="https://github.com/matthieupetite"/>
    <default name="projects" revision="main" remote="github"/>
    <project name="devcontainers" remote="github" path=".devcontainer" revision="go"/>
    <project name="infracost" remote="github" path="infracost" revision="refs/heads/feature/azure-sql-managed-instance" />
    <project name="docs" remote="github" path="infradoc" revision="refs/heads/feature/document-azure-sql-managed-instance" />
</manifest>
```

## Usefull link

- [Installing repo](https://source.android.com/setup/build/downloading#installing-repo)
