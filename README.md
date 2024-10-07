# Version Catalog - settings.gradle

This is the first example to use a [version catalog](https://docs.gradle.org/current/userguide/platforms.html).

The version catalog is defined in [settings.gradle](settings.gradle).
Similar to the BOM example, dependencies and their versions can be defined in the catalog and shared.
In addition to dependencies, version catalogs are also able to define plugins and bundles.

Plugins work similarly to dependencies, with the user being able to reference them from the catalog,
though the usage must be wrapped in an `alias` call.

```groovy
plugins {
    ...
    alias(libs.plugins.cyclonedx)
}
```

Bundles are a mechanism to combine multiple dependencies into a single reference. 
In this example, both the `junit-jupiter` and `assertj-core` dependencies are defined in a bundle called `testing`.

This bundle can then be referenced like any other dependency, with the one reference pulling in both dependencies:

```groovy
dependencies {
    testImplementation libs.bundles.testing
}
```

Being able to specify plugins and bundles allows version catalogs to make sharing common configuration even easier
than with the previous approaches.

In addition to this, when using an IDE like IntelliJ IDEA, the IDE can read the version catalog and provide
auto-completion when specifying anything from the version catalog.
This is useful when specifying known dependencies, but also offers the ability to discover other dependencies that
may be available.  
