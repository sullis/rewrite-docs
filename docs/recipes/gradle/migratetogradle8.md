---
sidebar_label: "Migrate to Gradle 8 from Gradle 7"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Migrate to Gradle 8 from Gradle 7

**org.openrewrite.gradle.MigrateToGradle8**

_Migrate to version 8.x. See the Gradle upgrade guide from [version 7.x to 8.0](https://docs.gradle.org/current/userguide/upgrading_version_7.html) and [version 8.x to latest](https://docs.gradle.org/current/userguide/upgrading_version_8.html) for more information._

## Recipe source

[GitHub](https://github.com/openrewrite/rewrite/blob/main/rewrite-gradle/src/main/resources/META-INF/rewrite/gradle-8.yml), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite/rewrite-gradle/8.36.0/jar)

* groupId: org.openrewrite
* artifactId: rewrite-gradle
* version: 8.36.0

:::info
This recipe is composed of more than one recipe. If you want to customize the set of recipes this is composed of, you can find and copy the GitHub source for the recipe from the link above.
:::

## Definition

<Tabs groupId="recipeType">
<TabItem value="recipe-list" label="Recipe List" >
* [Migrate to Gradle 7 from Gradle 6](../gradle/migratetogradle7)
* [Update Gradle wrapper](../gradle/updategradlewrapper)
  * version: `8.x`
  * addIfMissing: `false`
* [Remove an enabled Gradle preview feature](../gradle/removeenablefeaturepreview)
  * previewFeatureName: `ONE_LOCKFILE_PER_PROJECT`
* [Remove an enabled Gradle preview feature](../gradle/removeenablefeaturepreview)
  * previewFeatureName: `VERSION_ORDERING_V2`
* [Remove an enabled Gradle preview feature](../gradle/removeenablefeaturepreview)
  * previewFeatureName: `VERSION_CATALOGS`

</TabItem>

<TabItem value="yaml-recipe-list" label="Yaml Recipe List">

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.gradle.MigrateToGradle8
displayName: Migrate to Gradle 8 from Gradle 7
description: Migrate to version 8.x. See the Gradle upgrade guide from [version 7.x to 8.0](https://docs.gradle.org/current/userguide/upgrading_version_7.html) and [version 8.x to latest](https://docs.gradle.org/current/userguide/upgrading_version_8.html) for more information.
recipeList:
  - org.openrewrite.gradle.MigrateToGradle7
  - org.openrewrite.gradle.UpdateGradleWrapper:
      version: 8.x
      addIfMissing: false
  - org.openrewrite.gradle.RemoveEnableFeaturePreview:
      previewFeatureName: ONE_LOCKFILE_PER_PROJECT
  - org.openrewrite.gradle.RemoveEnableFeaturePreview:
      previewFeatureName: VERSION_ORDERING_V2
  - org.openrewrite.gradle.RemoveEnableFeaturePreview:
      previewFeatureName: VERSION_CATALOGS

```
</TabItem>
</Tabs>

## Usage

This recipe has no required configuration parameters and comes from a rewrite core library. It can be activated directly without adding any dependencies.
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:

```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.24.0")
}

rewrite {
    activeRecipe("org.openrewrite.gradle.MigrateToGradle8")
    exportDatatables = true
}

repositories {
    mavenCentral()
}

```
2. Run `gradle rewriteRun` to run the recipe.
</TabItem>

<TabItem value="gradle-init-script" label="Gradle init script">

1. Create a file named `init.gradle` in the root of your project.

```groovy title="init.gradle"
initscript {
    repositories {
        maven { url "https://plugins.gradle.org/m2" }
    }
    dependencies { classpath("org.openrewrite:plugin:latest.release") }
}
rootProject {
    plugins.apply(org.openrewrite.gradle.RewritePlugin)
    dependencies {
        rewrite("org.openrewrite:rewrite-java")
    }
    rewrite {
        activeRecipe("org.openrewrite.gradle.MigrateToGradle8")
        exportDatatables = true
    }
    afterEvaluate {
        if (repositories.isEmpty()) {
            repositories {
                mavenCentral()
            }
        }
    }
}
```

2. Run the recipe.

```shell title="shell"
gradle --init-script init.gradle rewriteRun
```
</TabItem>

<TabItem value="moderne-cli" label="Moderne CLI">

You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

```shell title="shell"
mod run . --recipe MigrateToGradle8
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/org.openrewrite.gradle.MigrateToGradle8">
    <img
    src={require("/static/img/ModerneRecipeButton.png").default}
    alt="Moderne Link Image"
    width="50%"
    />
</a>

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.
## Data Tables

### Source files that had results
**org.openrewrite.table.SourcesFileResults**

_Source files that were modified by the recipe run._

| Column Name | Description |
| ----------- | ----------- |
| Source path before the run | The source path of the file before the run. `null` when a source file was created during the run. |
| Source path after the run | A recipe may modify the source path. This is the path after the run. `null` when a source file was deleted during the run. |
| Parent of the recipe that made changes | In a hierarchical recipe, the parent of the recipe that made a change. Empty if this is the root of a hierarchy or if the recipe is not hierarchical at all. |
| Recipe that made changes | The specific recipe that made a change. |
| Estimated time saving | An estimated effort that a developer to fix manually instead of using this recipe, in unit of seconds. |
| Cycle | The recipe cycle in which the change was made. |

### Source files that errored on a recipe
**org.openrewrite.table.SourcesFileErrors**

_The details of all errors produced by a recipe run._

| Column Name | Description |
| ----------- | ----------- |
| Source path | The file that failed to parse. |
| Recipe that made changes | The specific recipe that made a change. |
| Stack trace | The stack trace of the failure. |

### Recipe performance
**org.openrewrite.table.RecipeRunStats**

_Statistics used in analyzing the performance of recipes._

| Column Name | Description |
| ----------- | ----------- |
| The recipe | The recipe whose stats are being measured both individually and cumulatively. |
| Source file count | The number of source files the recipe ran over. |
| Source file changed count | The number of source files which were changed in the recipe run. Includes files created, deleted, and edited. |
| Cumulative scanning time | The total time spent across the scanning phase of this recipe. |
| 99th percentile scanning time | 99 out of 100 scans completed in this amount of time. |
| Max scanning time | The max time scanning any one source file. |
| Cumulative edit time | The total time spent across the editing phase of this recipe. |
| 99th percentile edit time | 99 out of 100 edits completed in this amount of time. |
| Max edit time | The max time editing any one source file. |


## Contributors
[Shannon Pamperl](mailto:shanman190@gmail.com), [Ryan Walker](mailto:ryanwalker7@gmail.com), [Jonathan Schnéider](mailto:jkschneider@gmail.com), [Simon Hutchinson](mailto:simon.hutchinson@ixxus.com), [Sam Snyder](mailto:sam@moderne.io), [Tim te Beek](mailto:tim@moderne.io), [Jonathan Leitschuh](mailto:jonathan.leitschuh@gmail.com)