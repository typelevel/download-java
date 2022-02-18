# download-java

A GitHub Action for downloading JDKs. JDKs are provided by [typelevel/jdk-index](https://github.com/typelevel/jdk-index/) and are installed with [actions/setup-java](https://github.com/actions/setup-java).

### Example

```yaml
steps:
- uses: actions/checkout@v2
- uses: typelevel/download-java@v1
  id: download-java
  with:
    distribution: 'temurin'
    java-version: 17
- uses: actions/setup-java@v2
  with:
    distribution: 'jdkfile'
    java-version: 17
    jdkFile: ${{ steps.download-java.outputs.jdkFile }}
- run: java -version
```

Available distributions and versions are listed at [typelevel/jdk-index](https://github.com/typelevel/jdk-index/).
