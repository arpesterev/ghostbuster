# GhostBuster

GhostBuster is a Java library for describing document layouts and generating reports. The source combines XML-based layout and style definitions with a JasperReports adapter.

## Project structure

- **`GhostBuster`** defines the configuration model: tables, headers, rows, cells, layout, styles and positioning.
- **`JasperCompability`** (the module name as checked in) converts the configuration into JasperReports structures and renders documents.
- **`configuration.xml`** in the core module's resources is an example of the XML document model.

The main XML entry point is `ru.council.GhostBuster.Configuration`. `JasperReportsDocumentGenerator` provides the generation methods in the adapter module.

## Read the implementation

1. Start with [`Configuration.java`](subprojects/GhostBuster/src/main/java/ru/council/GhostBuster/Configuration.java) to understand the XML fields.
2. Review [`configuration.xml`](subprojects/GhostBuster/src/main/resources/configuration.xml) for layout syntax.
3. Follow [`JasperReportsDocumentGenerator.java`](subprojects/JasperCompability/src/main/java/ru/council/GhostBuster/jasper/generator/JasperReportsDocumentGenerator.java) to see how configuration and source data reach JasperReports.

## Build

The repository includes a multi-project Gradle build and wrapper:

```sh
./gradlew build
```

The build references `metan`, DXQL and a separate Maven package registry. A standalone build may need access to those artifacts and the `LIBS_PACKAGES_READ_TOKEN` environment variable.

This is a library snapshot, not a packaged report-design application. The build command is documented from the repository configuration and has not been verified in this update.
