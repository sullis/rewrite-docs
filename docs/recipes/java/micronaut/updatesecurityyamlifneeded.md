---
sidebar_label: "Update relocated Micronaut Security config yaml keys"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Update relocated Micronaut Security config yaml keys

**org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded**

_This recipe will update relocated security config keys in Micronaut configuration yaml files._

## Recipe source

[GitHub](https://github.com/openrewrite/rewrite-micronaut/blob/main/src/main/java/org/openrewrite/java/micronaut/UpdateSecurityYamlIfNeeded.java), [Issue Tracker](https://github.com/openrewrite/rewrite-micronaut/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-micronaut/2.9.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-micronaut
* version: 2.9.0

:::info
This recipe is composed of more than one recipe. If you want to customize the set of recipes this is composed of, you can find and copy the GitHub source for the recipe from the link above.
:::

## Definition

<Tabs groupId="recipeType">
<TabItem value="recipe-list" label="Recipe List" >
* [Merge YAML snippet](../../yaml/mergeyaml)
  * key: `$.micronaut.security.token`
  * yaml: `generator:   access-token:     expiration: cookie:   enabled:   cookie-max-age:   cookie-path:   cookie-domain:   cookie-same-site: bearer:   enabled:`
  * acceptTheirs: `true`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.generator.access-token.expiration`
  * newKey: `$.micronaut.security.token.generator.access-token.expiration`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.cookie.enabled`
  * newKey: `$.micronaut.security.token.cookie.enabled`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.cookie.cookie-max-age`
  * newKey: `$.micronaut.security.token.cookie.cookie-max-age`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.cookie.cookie-path`
  * newKey: `$.micronaut.security.token.cookie.cookie-path`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.cookie.cookie-domain`
  * newKey: `$.micronaut.security.token.cookie.cookie-domain`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.cookie.cookie-same-site`
  * newKey: `$.micronaut.security.token.cookie.cookie-same-site`
* [Copy YAML value](../../yaml/copyvalue)
  * oldKeyPath: `$.micronaut.security.token.jwt.bearer.enabled`
  * newKey: `$.micronaut.security.token.bearer.enabled`
* [Delete key](../../yaml/deletekey)
  * keyPath: `$.micronaut.security.token.jwt.generator`
* [Delete key](../../yaml/deletekey)
  * keyPath: `$.micronaut.security.token.jwt.cookie`
* [Delete key](../../yaml/deletekey)
  * keyPath: `$.micronaut.security.token.jwt.bearer`
* [Remove unused YAML](../../yaml/cleanup/removeunused)

</TabItem>

<TabItem value="yaml-recipe-list" label="Yaml Recipe List">

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded
displayName: Update relocated Micronaut Security config yaml keys
description: This recipe will update relocated security config keys in Micronaut configuration yaml files.
recipeList:
  - org.openrewrite.yaml.MergeYaml:
      key: $.micronaut.security.token
      yaml: generator:
  access-token:
    expiration:
cookie:
  enabled:
  cookie-max-age:
  cookie-path:
  cookie-domain:
  cookie-same-site:
bearer:
  enabled:
      acceptTheirs: true
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.generator.access-token.expiration
      newKey: $.micronaut.security.token.generator.access-token.expiration
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.cookie.enabled
      newKey: $.micronaut.security.token.cookie.enabled
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.cookie.cookie-max-age
      newKey: $.micronaut.security.token.cookie.cookie-max-age
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.cookie.cookie-path
      newKey: $.micronaut.security.token.cookie.cookie-path
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.cookie.cookie-domain
      newKey: $.micronaut.security.token.cookie.cookie-domain
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.cookie.cookie-same-site
      newKey: $.micronaut.security.token.cookie.cookie-same-site
  - org.openrewrite.yaml.CopyValue:
      oldKeyPath: $.micronaut.security.token.jwt.bearer.enabled
      newKey: $.micronaut.security.token.bearer.enabled
  - org.openrewrite.yaml.DeleteKey:
      keyPath: $.micronaut.security.token.jwt.generator
  - org.openrewrite.yaml.DeleteKey:
      keyPath: $.micronaut.security.token.jwt.cookie
  - org.openrewrite.yaml.DeleteKey:
      keyPath: $.micronaut.security.token.jwt.bearer
  - org.openrewrite.yaml.cleanup.RemoveUnused

```
</TabItem>
</Tabs>

## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-micronaut:2.9.0` in your build file or by running a shell command (in which case no build changes are needed): 
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:

```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.24.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded")
    exportDatatables = true
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-micronaut:2.9.0")
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
    dependencies { classpath("org.openrewrite:plugin:6.24.0") }
}
rootProject {
    plugins.apply(org.openrewrite.gradle.RewritePlugin)
    dependencies {
        rewrite("org.openrewrite.recipe:rewrite-micronaut:2.9.0")
    }
    rewrite {
        activeRecipe("org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded")
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
<TabItem value="maven" label="Maven POM">

1. Add the following to your `pom.xml` file:

```xml title="pom.xml"
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.41.0</version>
        <configuration>
          <exportDatatables>true</exportDatatables>
          <activeRecipes>
            <recipe>org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-micronaut</artifactId>
            <version>2.9.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```

2. Run `mvn rewrite:run` to run the recipe.
</TabItem>

<TabItem value="maven-command-line" label="Maven Command Line">
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

```shell title="shell"
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-micronaut:RELEASE -Drewrite.activeRecipes=org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded -Drewrite.exportDatatables=true
```
</TabItem>
<TabItem value="moderne-cli" label="Moderne CLI">

You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

```shell title="shell"
mod run . --recipe UpdateSecurityYamlIfNeeded
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/org.openrewrite.java.micronaut.UpdateSecurityYamlIfNeeded">
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
[Jeremy Grelle](mailto:grellej@unityfoundation.io), [Knut Wannheden](mailto:knut@moderne.io), [Tim te Beek](mailto:timtebeek@gmail.com), [Jonathan Schnéider](mailto:jkschneider@gmail.com)