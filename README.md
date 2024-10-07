# Version Catalog Generation

This example publishes a version catalog to be used by the 
[Shared Version Catalog Example](../../../tree/example/shared-catalog).

The example uses the [version-catalog plugin](https://docs.gradle.org/current/userguide/platforms.html#sec:version-catalog-plugin) 
to generate the version catalog.

To publish the version catalog to your local maven repository, run the following Gradle command:

```shell
./gradlew build publishToMavenLocal
```

The published version catalog can be found in your local maven repository at: 
`~/.m2/repository/org/global/owl/versions/example/version-catalog-demo`.
