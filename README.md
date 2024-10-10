# version-catalog-demo

This project contains examples demonstrating how [version catalogs](https://docs.gradle.org/current/userguide/platforms.html)
can be used in Gradle to share approved and/or validated libraries and plugins across one or more Gradle projects.

## Context

The project contains one test: [ExampleTest](src/test/java/org/global/owl/versions/example/ExampleTest.java).

This test requires the use of two libraries:

- `junit-jupiter` - [org.junit.jupiter:junit-jupiter:5.10.0](https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter/5.10.0)
- `assertj-core` - [org.junit.jupiter:junit-jupiter:3.24.2](https://mvnrepository.com/artifact/org.assertj/assertj-core/3.24.2)

The project has multiple git branches, each defining a dependency on these libraries in a different way.

In addition to dependencies,
the project also uses [CycloneDX Gradle Plugin](https://github.com/CycloneDX/cyclonedx-gradle-plugin)
as an example of how plugins can be shared in a version catalog.

## Examples

- [Hard-coded dependencies](/tree/example/hardcoded)
- [Define dependency versions as `ext` properties](/tree/example/ext)
- [Define dependency versions in `gradle.properties`](/tree/example/gradle-properties)
- [Define dependency versions in a custom BOM](/tree/example/bom)
- [Define dependency in a version catalog within `settings.gradle`](/tree/example/settings)
- [Define dependency in a .toml version catalog](/tree/example/gradle-tomly)
- [Define dependency in a shared version catalog](/tree/example/shared-catalog)

## Build

To build and run the test, use the following Gradle command when checked out to the example branch:

```shell
./gradlew clean build
```

Running this command will not work on the `main` branch, as the dependencies are not defined.

For some examples, you may also need to ensure that the artefacts they depend on have been generated locally.

__NOTE:__ This project uses the [example](/buildSrc/src/main/groovy/example.gradle) plugin defined in 
[buildSrc](buildSrc/README.md)
to configure the non-dependency or plugin related project options. 

