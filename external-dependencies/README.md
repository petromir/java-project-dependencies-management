# External Dependencies

A definition of Maven bom used to define all internal dependencies based on your project needs.

## Prerequisites
Refer to root [README](../README.md)

## Usage

### Maven
#### Import the bom
```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.petromirdzhunev</groupId>
            <artifactId>external-dependencies</artifactId>
            <version>${latest_external_dependencies_version}</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```
where `${latest_external_dependencies_version}` is the last created version in Nexus, e.g. `1.2.3`

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
            <artifactId>external-libs-bom</artifactId>
            <version>${latest_external_dependencies_version}-SNAPSHOT</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

## Tracking changes
The external dependencies are not under our control, and we don't have a guarantee that they will have a 
changelog and whether it will follow the required [format](https://keepachangelog.com/en/1.0.0/), so there is no 
need to put efforts in this direction.
