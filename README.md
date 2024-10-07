# Example: BOM

This example defines the dependencies required by the project in a 
[BOM](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html#Importing_Dependencies).

The BOM used in this project needs to be published to your local maven repository.
See [BOM Generation](../../../tree/publish-bom) for instructions.

To use the BOM, it is imported as 
a [platform dependency](https://docs.gradle.org/current/userguide/platforms.html#sub:bom_import):

```groovy
dependencies {
    testImplementation platform("org.global.owl.versions.example:version-catalog-demo-bom:0.0.0")
    testImplementation "org.junit.jupiter:junit-jupiter"
    testImplementation "org.assertj:assertj-core"
}
```

With a BOM published to a shared maven repository, the required dependencies can be shared across multiple projects.

To update the dependencies defined in the BOM, you only need to update the version of the BOM.

One downside to this approach is that you need to know what the BOM contains to be able to use the dependencies.
