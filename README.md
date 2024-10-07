# Example: gradle.properties

This example defines the dependencies required by the project directly in the [dependencies block](build.gradle), 
similarly to the `ext` properties example.

However, this example differs by specifying the versions for the dependencies inside 
[gradle.properties](gradle.properties).

```groovy
dependencies {
    testImplementation platform("org.junit:junit-bom:${junitVersion}")
    testImplementation "org.junit.jupiter:junit-jupiter"
    testImplementation "org.assertj:assertj-core:${assertjVersion}"
}
```

Similarly to `ext` properties, the versions are shared across all modules within the project.

By specifying the versions in the `gradle.properties` file, you don't need to try and find the `ext` block
within the project.
