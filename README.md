# BOM Generation

This example publishes a BOM to be used by the [BOM example](../../../tree/example/bom).

The example uses the [java-platform plugin](https://docs.gradle.org/current/userguide/java_platform_plugin.html) 
to generate the BOM.

To publish the BOM to your local maven repository, run the following Gradle command:

```shell
./gradlew clean publishToMavenLocal
```

The published BOM can be found in your local maven repository at: 
`~/.m2/repository/org/global/owl/versions/example/version-catalog-demo-bom`.