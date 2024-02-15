# Internal Dependencies

A definition of Maven bom used to define all internal dependencies based on your project needs.

## Prerequisites
Refer to root [README](../README.md)

## Usage

Address prerequisites defined in the root [README](../README.md) file first.

### Maven
#### Import the bom
```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.petromirdzhunev</groupId>
            <artifactId>internal-dependencies</artifactId>
            <version>${latest_internal_dependencies_version}</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```
where `${latest_internal_dependencies_version}` is the last distributed to Nexus, e.g. `1.2.3`

## Development

### Build and publish `SNAPSHOT` versions to local repository
Change the version by adding a `-SNAPSHOT` suffix in the [pom.xml](pom.xml) file and then execute:
```shell
 mvnd -B clean install
```

### Pointing to a local version
```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.petromirdzhunev</groupId>
            <artifactId>internal-libs-bom</artifactId>
            <version>${latest_internal_dependencies_version}-SNAPSHOT</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

## Tracking changes
The [following format](https://keepachangelog.com/en/1.0.0/) is used when describing changes in [CHANGELOG.md](CHANGELOG.md) file. 
The changelog for dependencies requires additional details as it combines changes from different 
projects.
When we have an addition, change, removal or fix that is a breaking one, then we should specify 
it with `[BREAKING]` prefix.

Here is the format:
```markdown
## [<version>] - <iso_date>

### Added

#### <dependency_name> [dependency_version]

- Addition 1
- Addition 2
...

### Changed

#### <dependency_name> [dependency_version]

- Change 1
- [BREAKING] Change 2
...

### Removed

#### <dependency_name> [dependency_version]

- Removed 1
- Removed 2 
...

### Fixed

#### <dependency_name> [dependency_version]

- Fix 1
- Fix 2
...

### Deprecated

#### <dependency_name> [dependency_version]

- Deprecated 1
- Deprecated 2
...

### Security

#### <dependency_name> [dependency_version]

- Security 1
- Security 2 
...
```