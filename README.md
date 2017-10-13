# brooklyn-jenkins
Apache Brooklyn blueprints for deploying Jenkins. The leading open source automation server, Jenkins provides hundreds of plugins to support building, deploying and automating any project.

### [For contributors] Release Process

#### Snapshot Release

In order to release a new snapshot version to Sonatype:

```bash
mvn deploy -DdeployTo=sonatype
```

#### Official Relesae

1. Create a new branch, e.g. `release/1.0.3`, and checkout that branch

2. Update the version running the command below (and double-check that pom.xml was correctly updated):

   ```bash
   GA_VERSION=1.0.3
   ~/repos/brooklyn/brooklyn-dist/release/change-version.sh BROOKLYN_JENKINS ${GA_VERSION}-SNAPSHOT ${GA_VERSION}
   ```

3. Confirm it builds: `mvn clean install`

4. Push release to sonatype, following the normal Sonatype process:

   ```bash
   mvn deploy -DdeployTo=sonatype
   ```
   