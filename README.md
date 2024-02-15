# Java Project Dependency Management Template

The project contains templates for managing internal and external dependencies using Maven

## Prerequisites
1. [Install SDKMAN](https://sdkman.io/install)
2. Initialize SDKMAN environment
```shell
sdk env install
```
3. Configure Maven settings
   - Copy [settings.xml](ci-cd/.m2/settings.xml) to your local `.m2` folder
   - Secure your Nexus password using the following [Maven guide](https://maven.apache.org/guides/mini/guide-encryption.html)
   - Replace username & password under `<server>` element

## Usage
- [external-dependencies](external-dependencies/README.md)
- [internal-dependencies](internal-dependencies/README.md)

## Distribution 
### Nexus
Distribution to Nexus is configured in two places:
1. `<distributionManagement>` tag in `pom.xml` files 
2. [settings.xml](ci-cd/.m2/settings.xml) file, passed to Maven during the deployment in GitLab pipeline.
[gitlab-ci.yml](ci-cd/gitlab/.gitlab-ci.yml) file defines the actual execution of the distribution

### GitLab Registry
**TBD**

### GitHub Packages
**TBD**

## TODO:
- Test Nexus
- Automatic version incrementation based using [Changelog rules](https://keepachangelog.com/en/1.1.0/)
- Add GitHub distribution to Nexus and [Packages](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry)
- Add GitLab distribution to Nexus GitLab Registry
