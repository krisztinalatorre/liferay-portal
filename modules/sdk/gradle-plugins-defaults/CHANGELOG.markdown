# Liferay Gradle Plugins Defaults Change Log

## 1.1.3 - 2016-08-22

### Changed
- [LPS-67658]: Update the [Liferay Gradle Plugins] dependency to version 2.0.10.

### Fixed
- [LPS-67658]: Compile the plugin against Gradle 2.14 to make it compatible with
both Gradle 2.14+ and Gradle 3.0.

## 1.1.4 - 2016-08-23

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.11.

## 1.1.5 - 2016-08-23

### Changed
- [LPS-67694]: Disable the `install` and `uploadArchives` tasks and all their
dependencies during the configuration phase if the `-PsnapshotIfStale` argument
is provided and the latest published snapshot is up-to-date.

### Fixed
- [LPS-67694]: Use Gradle to download the latest published artifact of a project
instead of the Nexus REST API, as the latter does not always return the correct
artifact.

## 1.1.6 - 2016-08-25

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.12.

## 1.1.7 - 2016-08-27

### Changed
- [LPS-67804]: Update the [Liferay Gradle Plugins] dependency to version 2.0.13.

## 1.1.8 - 2016-08-27

### Added
- [LPS-67023]: Automatically apply the following default settings when on
Jenkins:
	- Block Node.js invocations if the `com.liferay.cache` plugin is applied.
	- Enable the `node_modules` directory cache.
	- Retry `npm install` three times if a Node.js invocation fails.
	- Set up the NPM registry URL based on the `nodejs.npm.ci.registry` project
	property.

### Changed
- [LPS-67023]: Update the [Liferay Gradle Plugins] dependency to version 2.0.14.

## 1.1.9 - 2016-08-27

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.15.

## 1.1.10 - 2016-08-27

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.16.

## 1.1.11 - 2016-08-29

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.17.

## 1.1.12 - 2016-08-30

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.18.

## 1.1.13 - 2016-08-31

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.19.

## 1.2.0 - 2016-08-31

### Added
- [LPS-67863]: Allow the `Bundle-Version` and `packageinfo` versions of an OSGi
project to be overridden by creating a
`.version-overrides-${project.name}.properties` file in the parent directory of
the `.gitrepo` file with the following values:
	- `Bundle-Version=[new bundle version]`
	- `com.liferay.foo.bar=[new packageinfo version for com.liferay.foo.bar package]`

- [LPS-67863]: Execute the following actions when running `gradlew baseline
-PsyncRelease` on an OSGi project:
	1. Bump up the `Bundle-Version` and `packageinfo` versions based on the same
	module found in the branch defined in the `release.versions.test.other.dir`
	project property. The changes are either saved directly in the project
	files, or in the `.version-overrides-${project.name}.properties` file if the
	`.gitrepo` file contains the string `"mode = pull"`, which denotes a
	read-only sub-repository.
	2. Execute the `baseline` task, automatically ignoring any semantic
	versioning errors.
	3. Commit the project file changes caused by steps 1 and 2.

## 1.2.1 - 2016-08-31

### Fixed
- [LPS-67863]: Avoid Git error while running `gradlew baseline -PsyncRelease` on
an OSGi project that does not contain a `packageinfo` file.

## 1.2.2 - 2016-09-01

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.20.

## 1.2.3 - 2016-09-01

### Changed
- [LPS-67863]: The file that contains the version overrides for an OSGi module
is now called `.version-override-${project.name}.properties`.
- [LPS-67863]: The `packageinfo` versions are always overridden with the
versions specified in the `.version-override-${project.name}.properties` file,
even if the versions in the `packageinfo` files are greater.

## 1.2.4 - 2016-09-01

### Changed
- [LPS-67863]: Disable the `printArtifactPublishCommands` task if the project's
`build.gradle` contains the string `version: "default"`, to prevent releasing
modules with unpublished dependencies.
- [LPS-67863]: The `.version-override-${project.name}.properties` file now
contains only the version overrides that differ from the versions specified in
the `bnd.bnd` and `packageinfo` files.

## 1.2.5 - 2016-09-01

### Fixed
- [LPS-67863]: Avoid throwing an exception while running `gradlew baseline
-PsyncRelease` on a project that does not contain a
`.version-override-${project.name}.properties` file.

## 1.2.6 - 2016-09-02

### Fixed
- [LPS-67863]: Avoid throwing an exception while running the
`printArtifactPublishCommands` task on a project that does not contain a
`build.gradle` file.

## 1.2.7 - 2016-09-02

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.21.

## 1.2.8 - 2016-09-02

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.22.

## 1.2.9 - 2016-09-05

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.23.

## 1.2.10 - 2016-09-05

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.24.

## 1.2.11 - 2016-09-06

### Changed
- [LPS-67996]: Update the [Liferay Gradle Plugins] dependency to version 2.0.25.

## 1.2.12 - 2016-09-07

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.26.

## 1.2.13 - 2016-09-07

### Fixed
- [LPS-68009]: Reject snapshot artifacts while resolving the `baseline`
configuration.

## 1.2.14 - 2016-09-07

### Changed
- [LPS-68014]: Update the [Liferay Gradle Plugins] dependency to version 2.0.27.

## 1.2.15 - 2016-09-08

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.28.

## 1.2.16 - 2016-09-08

### Added
- [LPS-67863]: Allow dependency versions to be overridden in the
`.version-override-${project.name}.properties` file:

		[artifact group]-[artifact name]=[new version]

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.29.

## 1.2.17 - 2016-09-09

### Changed
- [LPS-61099]: Update the [Liferay Gradle Plugins] dependency to version 2.0.30.
- [LRDOCS-2841]: Look for the `.releng` directory starting from the project
directory instead of the root project directory. Doing this lets submodules like
`content-targeting` have their own separate `.releng` directory.

## 1.2.18 - 2016-09-12

### Changed
- [LPS-67766]: Update the [Liferay Gradle Plugins] dependency to version 2.0.31.

## 1.2.19 - 2016-09-13

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.32.

## 1.2.20 - 2016-09-13

### Changed
- [LPS-67986]: Update the [Liferay Gradle Plugins] dependency to version 2.0.33.

## 1.2.21 - 2016-09-13

### Changed
- [LRDOCS-2981]: Prepend *Module* string to `appJavadoc` module headings.

## 1.2.22 - 2016-09-14

### Changed
- [LPS-68131]: Update the [Liferay Gradle Plugins] dependency to version 2.0.34.

## 1.2.23 - 2016-09-16

### Changed
- [LPS-68131]: Update the [Liferay Gradle Plugins] dependency to version 2.0.35.

## 1.2.24 - 2016-09-20

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.36.
- [LPS-68230]: Configure [Liferay Gradle Plugins Node] to use version 6.6.0 of
Node.js.

### Removed
- [LPS-68230]: To reduce the number of plugins applied to a project and improve
performance, plugins in `com.liferay.gradle.plugins.defaults.internal` are no
longer applied via `apply plugin`.

## 1.2.25 - 2016-09-20

### Changed
- [LPS-66906]: Update the [Liferay Gradle Plugins] dependency to version 2.0.37.

## 1.2.26 - 2016-09-21

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.38.

## 1.2.27 - 2016-09-22

### Changed
- [LPS-68305]: Set the `buildService.buildNumberIncrement` property to `false`
by default.

## 1.2.28 - 2016-09-22

### Changed
- [LPS-68297]: Update the [Liferay Gradle Plugins] dependency to version 2.0.39.

## 1.2.29 - 2016-09-22

### Added
- [LPS-66906]: Override the [`sass-binary-path`](https://github.com/sass/node-sass#binary-configuration-parameters)
argument in the `npmInstall` task with the value of the project property
`nodejs.npm.ci.sass.binary.site` when using Jenkins.

### Changed
- [LPS-66906]: Update the [Liferay Gradle Plugins] dependency to version 2.0.40.

## 1.2.30 - 2016-09-23

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.41.

## 1.2.31 - 2016-09-23

### Added
- [LPS-68306]: Set the system property `portal.pre.build` to `true` to only
include the projects containing a `.lfrbuild-portal-pre` marker file.

## 1.2.32 - 2016-09-26

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.42.

## 1.2.33 - 2016-09-27

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 2.0.44.

## 1.2.34 - 2016-09-27

### Changed
- [LPS-67863]: Change dependency version override declarations in
`.version-override-${project.name}.properties` to follow a new format:

		[artifact group]/[artifact name]=[new version]

### Fixed
- [LPS-67863]: Fix commit deletion process of version override files.

## 1.2.35 - 2016-09-28

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.45.

## 1.2.36 - 2016-09-29

### Changed
- [LPS-58672]: Update the [Liferay Gradle Plugins] dependency to version 2.0.46.

## 1.2.37 - 2016-09-30

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 2.0.47.

## 1.2.38 - 2016-10-01

### Added
- [LPS-68448]: Fail the build of an OSGi project if the version in the
`npm-shrinkwrap.json` file does not match the project version.
- [LPS-68448]: The task `updateVersion` of OSGi and theme projects updates the
version in the `npm-shrinkwrap.json` file, if present.

## 1.2.39 - 2016-10-03

### Added
- [LPS-68402]: Set the [`org.apache.maven.offline`](https://github.com/shrinkwrap/resolver#system-properties)
system property to `true` for the `testIntegration` task.

### Changed
- [LPS-68485]: Update the [Liferay Gradle Plugins] dependency to version 2.0.48.

## 1.2.40 - 2016-10-04

### Added
- [LPS-68506]: Exclude unpublished projects from the API documentation generated
by the `appJavadoc` task.

### Changed
- [LPS-68504]: Update the [Liferay Gradle Plugins] dependency to version 2.0.49.
- [LPS-68506]: Update the [Liferay Gradle Plugins App Javadoc Builder]
dependency to version 1.1.0.

## 1.2.41 - 2016-10-05

### Added
- [LPS-68540]: Fail the `uploadArchives` task execution if the project directory
contains the marker file `.lfrbuild-missing-resources-importer`.

## 1.2.42 - 2016-10-05

### Added
- [LPS-66396]: Exclude specific project types from the build by setting the
following system properties to `true`:
	- `build.exclude.ant.plugin` to exclude all projects that contain a
	`build.xml` file from the build.
	- `build.exclude.module` to exclude all projects that contain a `bnd.bnd`
	file from the build.
	- `build.exclude.theme` to exclude all projects that contain a `gulpfile.js`
	file from the build.

### Removed
- [LPS-66396]: The `modules.only.build` system property is no longer available.

## 1.2.43 - 2016-10-05

### Changed
- [LPS-68334]: Update the [Liferay Gradle Plugins] dependency to version 2.0.50.

## 1.2.44 - 2016-10-06

### Changed
- [LPS-66396]: Update the [Liferay Gradle Plugins] dependency to version 3.0.0.

### Fixed
- [LPS-66396]: Update import in several classes from
`java.io.UncheckedIOException` to `org.gradle.api.UncheckedIOException` to
remove Java 8 dependency.

## 1.2.45 - 2016-10-06

### Changed
- [LPS-68415]: Update the [Liferay Gradle Plugins] dependency to version 3.0.1.

## 1.2.46 - 2016-10-06

### Added
- [LPS-68564]: Bypass https://github.com/npm/npm/issues/14042 and always exclude
the `fsevents` dependency from the generated `npm-shrinkwrap.json` files.

### Changed
- [LPS-68564]: Update the [Liferay Gradle Plugins] dependency to version 3.0.2.

## 1.2.47 - 2016-10-07

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 3.0.3.

## 1.2.48 - 2016-10-07

### Added
- [LRDOCS-3023]: The `com.liferay.app.defaults.plugin` now automatically adds
the local Maven and [Liferay CDN] repositories to the project.
- [LRDOCS-3023]: The `com.liferay.app.defaults.plugin` now automatically applies
the `com.liferay.app.tlddoc.builder` plugin.

### Changed
- [LRDOCS-3023]: Update the [Liferay Gradle Plugins] dependency to version
3.0.4.

## 1.2.49 - 2016-10-10

### Added
- [LPS-68611]: Update the [Liferay Gradle Plugins] dependency to version 3.0.5.
- [LRDOCS-2594]: Apply the [Liferay stylesheet](https://github.com/liferay/liferay-portal/blob/master/tools/styles/javadoc.css)
file, if found, to the API documentation generated by the `appJavadoc` and
`javadoc` tasks.

## 1.2.50 - 2016-10-10

### Changed
- [LPS-68618]: Update the [Liferay Gradle Plugins] dependency to version 3.0.6.

## 1.2.51 - 2016-10-11

### Changed
- [LPS-68598]: Update the [Liferay Gradle Plugins] dependency to version 3.0.7.

## 1.2.52 - 2016-10-11

### Added
- [LPS-68650]: Automatically update the versions in `npm-shrinkwrap.json` and
`package.json` files after running the `baseline` task.

## 1.2.53 - 2016-10-11

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.8.

## 1.2.54 - 2016-10-12

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 3.0.9.

## 1.2.55 - 2016-10-12

### Added
- [LPS-68666]: Include the subprojects of the private counterpart, if found, in
the API and tag library documentations of an app.

### Changed
- [LPS-68666]: Update the [Liferay Gradle Plugins] dependency to version 3.0.10.
- [LPS-68666]: Update the [Liferay Gradle Plugins App Javadoc Builder]
dependency to version 1.2.0.

### Fixed
- [LPS-68666]: Set the `title` property of the `appJavadoc` task based on the
`app.properties` file of the private counterpart, if found. This way, the API
documentation of the app, when generated from a private branch, will display the
latest published version of the private app.

## 1.2.56 - 2016-10-13

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 3.0.11.
- [LRDOCS-3038]: Include the bundle symbolic name in the API documentation title
generated by the `javadoc` task.

## 1.2.57 - 2016-10-13

### Removed
- [LPS-68448]: Temporarily disable `npm-shrinkwrap.json` version check.

## 1.2.58 - 2016-10-13

### Removed
- [LPS-68448]: Temporarily disable `package.json` version check.

## 1.2.59 - 2016-10-13

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.12.

## 1.2.60 - 2016-10-17

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.13.

## 1.2.61 - 2016-10-17

### Added
- [LPS-68772]: Allow module dependencies to be overridden with project
dependencies in the `.version-override-${project.name}.properties` file:

		[artifact group]/[artifact name]=[project path]

## 1.2.62 - 2016-10-17

### Changed
- [LPS-68779]: Update the [Liferay Gradle Plugins] dependency to version 3.0.14.

## 1.2.63 - 2016-10-18

### Added
- [LPS-68817]: Set the system property `build.profile` to only include projects
containing a `.lfrbuild-portal-${build.profile}` marker file.

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.15.

### Removed
- [LPS-68817]: The system property `portal.build` is no longer available; use
the `-Dbuild.profile=portal` parameter instead.
- [LPS-68817]: The system property `portal.pre.build` is no longer available;
use the `-Dbuild.profile=portal-pre` parameter instead.

## 1.2.64 - 2016-10-18

### Changed
- [LPS-68779]: Update the [Liferay Gradle Plugins] dependency to version 3.0.16.

## 1.2.65 - 2016-10-19

### Added
- [LPS-68448]: If the version override file of the project declares a different
version, update the `npm-shrinkwrap.json` and `package.json` files accordingly.

### Fixed
- [LPS-68448]: Restore `npm-shrinkwrap.json` and `package.json` version checks.

## 1.2.66 - 2016-10-19

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.17.

## 1.2.67 - 2016-10-20

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.18.

## 1.2.68 - 2016-10-20

### Changed
- [LPS-67434]: Update the [Liferay Gradle Plugins] dependency to version 3.0.19.

## 1.2.69 - 2016-10-20

### Changed
- [LPS-68839]: Update the [Liferay Gradle Plugins] dependency to version 3.0.20.

## 1.2.70 - 2016-10-21

### Changed
- [LPS-68838]: Update the [Liferay Gradle Plugins] dependency to version 3.0.21.

## 1.2.71 - 2016-10-21

### Changed
- [LPS-66906]: Update the [Liferay Gradle Plugins] dependency to version 3.0.22.

## 1.2.72 - 2016-10-24

### Changed
- [LPS-68917]: Update the [Liferay Gradle Plugins] dependency to version 3.0.23.

## 1.2.73 - 2016-10-25

### Changed
- [LPS-52675]: Update the [Liferay Gradle Plugins] dependency to version 3.0.25.

## 1.2.74 - 2016-10-25

### Added
- [LPS-68935]: Set the Maven description to the project description when
publishing.

## 1.2.75 - 2016-10-26

### Changed
- [LPS-68917]: Update the [Liferay Gradle Plugins] dependency to version 3.0.26.

## 1.2.76 - 2016-10-27

### Changed
- [LPS-68980]: Update the [Liferay Gradle Plugins] dependency to version 3.0.27.

## 1.2.77 - 2016-10-28

*No changes.*

## 1.2.78 - 2016-10-31

### Changed
- [LPS-69013]: Update the [Liferay Gradle Plugins] dependency to version 3.0.29.

## 1.2.79 - 2016-10-31

### Changed
- [LPS-69013]: Update the [Liferay Gradle Plugins] dependency to version 3.0.30.

## 1.2.80 - 2016-11-01

### Changed
- [LPS-68293]: Update the [Liferay Gradle Plugins] dependency to version 3.0.31.

## 1.2.81 - 2016-11-01

### Changed
- [LPS-69026]: Update the [Liferay Gradle Plugins] dependency to version 3.0.32.

## 1.2.82 - 2016-11-02

### Changed
- [LPS-68293]: Update the [Liferay Gradle Plugins] dependency to version 3.0.33.

## 1.2.83 - 2016-11-03

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.34.

## 1.2.84 - 2016-11-03

### Changed
- [LPS-68298]: Update the [Liferay Gradle Plugins] dependency to version 3.0.35.

## 1.2.85 - 2016-11-04

### Changed
- [LPS-68298]: Update the [Liferay Gradle Plugins] dependency to version 3.0.36.

## 2.0.0 - 2016-11-17

### Changed
- [LPS-66762]: Apply [Liferay Gradle Plugins Baseline].
- [LPS-67573]: Make most methods private in order to reduce API surface.
- [LPS-69223]: Update the [Liferay Gradle Plugins] dependency to version 3.0.37.

### Removed
- [LPS-66762]: The `BaselineTask` class is no longer available. Use the class in
[Liferay Gradle Plugins Baseline] instead.
- [LPS-67573]: Remove all deprecated methods.

## 2.0.1 - 2016-11-21

### Added
- [LPS-69288]: Set the `app.description` project property to override the
project description if the `com.liferay.app.defaults.plugin` is applied.
- [LPS-69288]: Set the `app.title` project property to override the title used
in the `appJavadoc` task.
- [LPS-69288]: Set the `app.version` project property to override the project
version if the `com.liferay.app.defaults.plugin` is applied.

### Changed
- [LPS-69271]: Update the [Liferay Gradle Plugins] dependency to version 3.0.38.

## 2.0.2 - 2016-11-22

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.39.

## 2.0.3 - 2016-11-23

### Changed
- [LPS-66853]: Update the [Liferay Gradle Plugins] dependency to version 3.0.40.

## 2.0.4 - 2016-11-24

### Changed
- [LPS-69271]: Update the [Liferay Gradle Plugins] dependency to version 3.0.41.

## 2.0.5 - 2016-11-28

### Changed
- [LPS-67352]: Update the [Liferay Gradle Plugins] dependency to version 3.0.42.

## 2.0.6 - 2016-11-29

### Added
- [LPS-68813]: Add task `findSecurityBugs` to check for security problems.

### Changed
- [LPS-69445]: Update the [Liferay Gradle Plugins] dependency to version 3.0.43.

## 2.0.7 - 2016-11-30 [YANKED]

### Changed
- [LPS-69470]: Update the [Liferay Gradle Plugins Baseline] dependency to
version 1.1.0.

## 2.0.8 - 2016-12-01

### Changed
- [LPS-69488]: Update the [Liferay Gradle Plugins] dependency to version 3.0.44.

### Removed
- [LPS-69488]: Remove the default Node.js version configuration, as it has been
moved to [Liferay Gradle Plugins].

## 2.0.9 - 2016-12-01

### Changed
- [LPS-69492]: Update the [Liferay Gradle Plugins] dependency to version 3.0.45.

[Liferay CDN]: https://cdn.lfrs.sl/repository.liferay.com/nexus/content/groups/public
[Liferay Gradle Plugins]: https://github.com/liferay/liferay-portal/tree/master/modules/sdk/gradle-plugins
[Liferay Gradle Plugins App Javadoc Builder]: https://github.com/liferay/liferay-portal/tree/master/modules/sdk/gradle-plugins-app-javadoc-builder
[Liferay Gradle Plugins Baseline]: https://github.com/liferay/liferay-portal/tree/master/modules/sdk/gradle-plugins-baseline
[Liferay Gradle Plugins Node]: https://github.com/liferay/liferay-portal/tree/master/modules/sdk/gradle-plugins-node
[LPS-52675]: https://issues.liferay.com/browse/LPS-52675
[LPS-58672]: https://issues.liferay.com/browse/LPS-58672
[LPS-61099]: https://issues.liferay.com/browse/LPS-61099
[LPS-66396]: https://issues.liferay.com/browse/LPS-66396
[LPS-66396]: https://issues.liferay.com/browse/LPS-66396
[LPS-66762]: https://issues.liferay.com/browse/LPS-66762
[LPS-66853]: https://issues.liferay.com/browse/LPS-66853
[LPS-66906]: https://issues.liferay.com/browse/LPS-66906
[LPS-67023]: https://issues.liferay.com/browse/LPS-67023
[LPS-67352]: https://issues.liferay.com/browse/LPS-67352
[LPS-67434]: https://issues.liferay.com/browse/LPS-67434
[LPS-67573]: https://issues.liferay.com/browse/LPS-67573
[LPS-67658]: https://issues.liferay.com/browse/LPS-67658
[LPS-67694]: https://issues.liferay.com/browse/LPS-67694
[LPS-67766]: https://issues.liferay.com/browse/LPS-67766
[LPS-67804]: https://issues.liferay.com/browse/LPS-67804
[LPS-67863]: https://issues.liferay.com/browse/LPS-67863
[LPS-67986]: https://issues.liferay.com/browse/LPS-67986
[LPS-67996]: https://issues.liferay.com/browse/LPS-67996
[LPS-68009]: https://issues.liferay.com/browse/LPS-68009
[LPS-68014]: https://issues.liferay.com/browse/LPS-68014
[LPS-68131]: https://issues.liferay.com/browse/LPS-68131
[LPS-68230]: https://issues.liferay.com/browse/LPS-68230
[LPS-68293]: https://issues.liferay.com/browse/LPS-68293
[LPS-68297]: https://issues.liferay.com/browse/LPS-68297
[LPS-68298]: https://issues.liferay.com/browse/LPS-68298
[LPS-68305]: https://issues.liferay.com/browse/LPS-68305
[LPS-68306]: https://issues.liferay.com/browse/LPS-68306
[LPS-68334]: https://issues.liferay.com/browse/LPS-68334
[LPS-68402]: https://issues.liferay.com/browse/LPS-68402
[LPS-68415]: https://issues.liferay.com/browse/LPS-68415
[LPS-68448]: https://issues.liferay.com/browse/LPS-68448
[LPS-68485]: https://issues.liferay.com/browse/LPS-68485
[LPS-68504]: https://issues.liferay.com/browse/LPS-68504
[LPS-68506]: https://issues.liferay.com/browse/LPS-68506
[LPS-68540]: https://issues.liferay.com/browse/LPS-68540
[LPS-68564]: https://issues.liferay.com/browse/LPS-68564
[LPS-68598]: https://issues.liferay.com/browse/LPS-68598
[LPS-68611]: https://issues.liferay.com/browse/LPS-68611
[LPS-68618]: https://issues.liferay.com/browse/LPS-68618
[LPS-68650]: https://issues.liferay.com/browse/LPS-68650
[LPS-68666]: https://issues.liferay.com/browse/LPS-68666
[LPS-68772]: https://issues.liferay.com/browse/LPS-68772
[LPS-68779]: https://issues.liferay.com/browse/LPS-68779
[LPS-68813]: https://issues.liferay.com/browse/LPS-68813
[LPS-68817]: https://issues.liferay.com/browse/LPS-68817
[LPS-68838]: https://issues.liferay.com/browse/LPS-68838
[LPS-68839]: https://issues.liferay.com/browse/LPS-68839
[LPS-68917]: https://issues.liferay.com/browse/LPS-68917
[LPS-68935]: https://issues.liferay.com/browse/LPS-68935
[LPS-68980]: https://issues.liferay.com/browse/LPS-68980
[LPS-69013]: https://issues.liferay.com/browse/LPS-69013
[LPS-69026]: https://issues.liferay.com/browse/LPS-69026
[LPS-69223]: https://issues.liferay.com/browse/LPS-69223
[LPS-69271]: https://issues.liferay.com/browse/LPS-69271
[LPS-69288]: https://issues.liferay.com/browse/LPS-69288
[LPS-69445]: https://issues.liferay.com/browse/LPS-69445
[LPS-69470]: https://issues.liferay.com/browse/LPS-69470
[LPS-69488]: https://issues.liferay.com/browse/LPS-69488
[LPS-69492]: https://issues.liferay.com/browse/LPS-69492
[LRDOCS-2594]: https://issues.liferay.com/browse/LRDOCS-2594
[LRDOCS-2841]: https://issues.liferay.com/browse/LRDOCS-2841
[LRDOCS-2981]: https://issues.liferay.com/browse/LRDOCS-2981
[LRDOCS-3023]: https://issues.liferay.com/browse/LRDOCS-3023
[LRDOCS-3038]: https://issues.liferay.com/browse/LRDOCS-3038