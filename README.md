# Example: Hard-coded Properties

This example defines the dependencies required by the project directly in the [dependencies block](build.gradle):

```groovy
dependencies {
    testImplementation platform("org.junit:junit-bom:5.10.0")
    testImplementation "org.junit.jupiter:junit-jupiter"
    testImplementation "org.assertj:assertj-core:3.24.2"
}
```

This works well for a single project, but can become more painful when needing to share these dependencies across
multiple modules or projects.

For a single project with multiple modules, common dependencies can be added to a `subprojects` block.
However,
it is [recommended
to avoid this approach](https://docs.gradle.org/current/userguide/sharing_build_logic_between_subprojects.html#sec:convention_plugins_vs_cross_configuration).

If you wanted to share these dependencies across multiple projects, you would have to copy/paste these 
dependencies into each project. 
This can cause more work if you need to align these dependencies, as you will have to update each dependency in each
project manually. 
