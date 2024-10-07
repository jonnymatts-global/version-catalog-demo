# Example: Shared Version Catalog

This example defines the dependencies required by the project in a version catalog published to a maven repository.

The version catalog used in this project needs to be published to your local maven repository.
See [Version Catalog Generation](../../../tree/publish-version-catalog) for instructions.

To use the version catalog, it needs to be defined as a dependency resolution source in [settings.gradle](settings.gradle):

```groovy
dependencyResolutionManagement {
    versionCatalogs {
        libs {
            from("org.global.owl.versions.example:version-catalog-demo:0.0.0")
        }
    }
}
```

With a version catalog published to a shared maven repository, 
the required dependencies, plugins, and bundles can be shared across multiple projects.

To update the dependencies defined in the version catalog, you only need to update the version of the version catalog.

This approach has all the benefits of the shared BOM example, with the addition of the version catalog also providing
auto-completion and dependency discovery in an IDE.
