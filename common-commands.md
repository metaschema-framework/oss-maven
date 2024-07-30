# Common development-related commands

## License Management

To check preamble is included in all source files:

```bash
mvn license:check
```

To add the preamble to all source files:

```bash
mvn license:format
```

## Source Formatting

To check source formatting:

```bash
mvn formatter:validate
```

To reformat all Java sources:

```bash
mvn formatter:format
```

## Source Validation

To check for other source issues (e.g., Javadoc):

```bash
mvn checkstyle:check
```

# Release-Related Commands

## Tagging a release

To perform a release on `develop` or a release branch:

```bash
mvn -Prelease -Preporting release:clean release:prepare
```

No need to include the `release:perform` goal, since this is handled by the GitHub actions CI/CD.

## Building the website

To build the website:

```bash
mvn -Preporting site site:stage
```

## Build Management

To look at the build plan:

```bash
mvn -Prelease -Preporting  fr.jcgay.maven.plugins:buildplan-maven-plugin:list-phase -Dbuildplan.tasks="deploy,site"
```

To look at the effective POM:

```bash
mvn -Prelease -Preporting help:effective-pom
```
