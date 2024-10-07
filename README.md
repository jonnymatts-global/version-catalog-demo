# Example: ext Properties

This example defines the dependencies required by the project directly in the [dependencies block](build.gradle), 
similarly to the hard-coded properties example.

However, this example differs by providing the versions for the dependencies inside 
an [ext properties block](https://docs.gradle.org/current/userguide/writing_build_scripts.html#sec:extra_properties).

```groovy
ext["junitVersion"] = "5.10.0"
ext["assertjVersion"] = "3.24.2"

dependencies {
    testImplementation platform("org.junit:junit-bom:${junitVersion}")
    testImplementation "org.junit.jupiter:junit-jupiter"
    testImplementation "org.assertj:assertj-core:${assertjVersion}"
}
```

By adding the versions as `ext` properties, the versions are shared across all modules within the project.

By specifying the versions separately, it is slightly easier to know where to change when updating dependencies.
