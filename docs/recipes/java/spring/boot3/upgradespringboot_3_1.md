---
sidebar_label: "Migrate to Spring Boot 3.1"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Migrate to Spring Boot 3.1

**org.openrewrite.java.spring.boot3.UpgradeSpringBoot\_3\_1**

_Migrate applications to the latest Spring Boot 3.1 release. This recipe will modify an application's build files, make changes to deprecated/preferred APIs, and migrate configuration settings that have changes between versions. This recipe will also chain additional framework migrations (Spring Framework, Spring Data, etc) that are required as part of the migration to Spring Boot 3.0._

### Tags

* spring
* boot

## Recipe source

[GitHub](https://github.com/openrewrite/rewrite-spring/blob/main/src/main/resources/META-INF/rewrite/spring-boot-31.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-spring/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-spring/5.20.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-spring
* version: 5.20.0

:::info
This recipe is composed of more than one recipe. If you want to customize the set of recipes this is composed of, you can find and copy the GitHub source for the recipe from the link above.
:::

## Definition

<Tabs groupId="recipeType">
<TabItem value="recipe-list" label="Recipe List" >
* [Migrate to Spring Boot 3.0](../../../java/spring/boot3/upgradespringboot_3_0)
* [Upgrade Gradle or Maven dependency versions](../../../java/dependencies/upgradedependencyversion)
  * groupId: `org.springframework.boot`
  * artifactId: `*`
  * newVersion: `3.1.x`
  * overrideManagedVersion: `false`
* [Upgrade Maven plugin version](../../../maven/upgradepluginversion)
  * groupId: `org.springframework.boot`
  * artifactId: `spring-boot-maven-plugin`
  * newVersion: `3.1.x`
* [Upgrade Maven parent project version](../../../maven/upgradeparentversion)
  * groupId: `org.springframework.boot`
  * artifactId: `spring-boot-starter-parent`
  * newVersion: `3.1.x`
* [Update a Gradle plugin by id](../../../gradle/plugins/upgradepluginversion)
  * pluginIdPattern: `org.springframework.boot`
  * newVersion: `3.1.x`
* [Migrate to Spring Security 6.1](../../../java/spring/security6/upgradespringsecurity_6_1)
* [Migrate Spring Boot properties to 3.1](../../../java/spring/boot3/springbootproperties_3_1)
* [Upgrade Gradle or Maven dependency versions](../../../java/dependencies/upgradedependencyversion)
  * groupId: `org.springdoc`
  * artifactId: `*`
  * newVersion: `2.2.x`
* [Migrate to Hibernate 6.2.x](../../../hibernate/migratetohibernate62)
* [Migrate to Reactor 3.5](../../../reactive/reactor/upgradereactor_3_5)

</TabItem>

<TabItem value="yaml-recipe-list" label="Yaml Recipe List">

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_1
displayName: Migrate to Spring Boot 3.1
description: Migrate applications to the latest Spring Boot 3.1 release. This recipe will modify an application's build files, make changes to deprecated/preferred APIs, and migrate configuration settings that have changes between versions. This recipe will also chain additional framework migrations (Spring Framework, Spring Data, etc) that are required as part of the migration to Spring Boot 3.0.
tags:
  - spring
  - boot
recipeList:
  - org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_0
  - org.openrewrite.java.dependencies.UpgradeDependencyVersion:
      groupId: org.springframework.boot
      artifactId: *
      newVersion: 3.1.x
      overrideManagedVersion: false
  - org.openrewrite.maven.UpgradePluginVersion:
      groupId: org.springframework.boot
      artifactId: spring-boot-maven-plugin
      newVersion: 3.1.x
  - org.openrewrite.maven.UpgradeParentVersion:
      groupId: org.springframework.boot
      artifactId: spring-boot-starter-parent
      newVersion: 3.1.x
  - org.openrewrite.gradle.plugins.UpgradePluginVersion:
      pluginIdPattern: org.springframework.boot
      newVersion: 3.1.x
  - org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_1
  - org.openrewrite.java.spring.boot3.SpringBootProperties_3_1
  - org.openrewrite.java.dependencies.UpgradeDependencyVersion:
      groupId: org.springdoc
      artifactId: *
      newVersion: 2.2.x
  - org.openrewrite.hibernate.MigrateToHibernate62
  - org.openrewrite.reactive.reactor.UpgradeReactor_3_5

```
</TabItem>
</Tabs>

## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-spring:5.20.0` in your build file or by running a shell command (in which case no build changes are needed): 
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:

```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.24.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_1")
    exportDatatables = true
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-spring:5.20.0")
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
        rewrite("org.openrewrite.recipe:rewrite-spring:5.20.0")
    }
    rewrite {
        activeRecipe("org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_1")
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
            <recipe>org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_1</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-spring</artifactId>
            <version>5.20.0</version>
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
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-spring:RELEASE -Drewrite.activeRecipes=org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_1 -Drewrite.exportDatatables=true
```
</TabItem>
<TabItem value="moderne-cli" label="Moderne CLI">

You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

```shell title="shell"
mod run . --recipe UpgradeSpringBoot_3_1
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/org.openrewrite.java.spring.boot3.UpgradeSpringBoot_3_1">
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
Tyler Van Gorder, [Knut Wannheden](mailto:knut@moderne.io), [Tim te Beek](mailto:tim@moderne.io), [Nick McKinney](mailto:mckinneynichoals@gmail.com), [Patrick](mailto:patway99@gmail.com), [Alex Boyko](mailto:aboyko@vmware.com), Chuka Obinabo, [Jonathan Schnéider](mailto:jkschneider@gmail.com), [Jonathan Schneider](mailto:jkschneider@gmail.com), Kun Li, [traceyyoshima](mailto:tracey.yoshima@gmail.com), [Joan Viladrosa](mailto:joan@moderne.io), pdesprez, Anu Ramamoorthy, [Kyle Scully](mailto:scullykns@gmail.com), [Sam Snyder](mailto:sam@moderne.io), Patrick Way, [Aaron Gershman](mailto:aegershman@gmail.com), [Laurens Westerlaken](mailto:laurens.w@live.nl), [Satvika Eda](mailto:satvika164.reddy@gmail.com), [Nick McKinney](mailto:mckinneynicholas@gmail.com), [Shannon Pamperl](mailto:shanman190@gmail.com), Simon Zilliken, [Tim te Beek](mailto:tim.te.beek@jdriven.com), [Kevin McCarpenter](mailto:kevin@moderne.io), [Kun Li](mailto:kun@moderne.io), Fabian Krüger, [Tim te Beek](mailto:timtebeek@gmail.com), Evie Lau, Adam Slaski, [Yifeng Jin](mailto:yifeng.jyf@alibaba-inc.com), [Johannes Jank](mailto:johannes.wengert@googlemail.com), Michel Gonzalez, Aaron Gershman, ranuradh, nbruno, BhavanaPidapa, Daryl Robbins, Sandeep Nagaraj, [Simon Verhoeven](mailto:verhoeven.simon@gmail.com), [Tracey Yoshima](mailto:tracey.yoshima@gmail.com), [BoykoAlex](mailto:aboyko@pivotal.io), BramliAK, [Michael Keppler](mailto:bananeweizen@gmx.de), [Jonathan Leitschuh](mailto:jonathan.leitschuh@gmail.com), Aakarshit Uppal, Josh Soref, eocantu, Adriano Machado