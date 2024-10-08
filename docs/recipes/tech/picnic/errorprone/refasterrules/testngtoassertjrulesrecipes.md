---
sidebar_label: "Refaster rules that replace TestNG assertions with equivalent AssertJ assertions"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Refaster rules that replace TestNG assertions with equivalent AssertJ assertions

**tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes**

```
<p>Some of the classes below have TestNG `@BeforeTemplate`s that reference wildcard type
 bounds (`<?>`), while the associated AssertJ `@AfterTemplate`s reference stricter
 type bounds. This introduces the risk of producing invalid code. We do this anyway, because
 TestNG's wildcard types can cause javac to infer less specific types than AssertJ requires, while
 the appropriate (more specific) types _will_ be inferred properly when plugged into AssertJ's
 API.

 <p>The following is an example of a TestNG statement, which would not be rewritten if it weren't
 for the wildcard matching (note that the type parameters of the map on the right-hand side will
 be inferred to be `<Object, Object>` rather than `<String, Object>`).

 <pre>{@code
 List<Map<String, Object>> myMaps = new ArrayList<>();
 assertEquals(myMaps, ImmutableList.of(ImmutableMap.of()));
 }</pre>. [Source](https://error-prone.picnic.tech/refasterrules/TestNGToAssertJRules).
```


## Recipe source

[GitHub](https://github.com/search?type=code&q=tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes), [Issue Tracker](https://github.com/openrewrite/rewrite-third-party/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-third-party/0.8.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-third-party
* version: 0.8.0

:::info
This recipe is composed of more than one recipe. If you want to customize the set of recipes this is composed of, you can find and copy the GitHub source for the recipe from the link above.
:::

## Definition

<Tabs groupId="recipeType">
<TabItem value="recipe-list" label="Recipe List" >
* [Refaster template `TestNGToAssertJRules.Fail`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$failrecipe)
* [Refaster template `TestNGToAssertJRules.FailWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$failwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.FailWithMessageAndThrowable`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$failwithmessageandthrowablerecipe)
* [Refaster template `TestNGToAssertJRules.AssertTrue`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$asserttruerecipe)
* [Refaster template `TestNGToAssertJRules.AssertTrueWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$asserttruewithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertFalse`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertfalserecipe)
* [Refaster template `TestNGToAssertJRules.AssertFalseWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertfalsewithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertNull`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertnullrecipe)
* [Refaster template `TestNGToAssertJRules.AssertNullWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertnullwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertNotNull`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertnotnullrecipe)
* [Refaster template `TestNGToAssertJRules.AssertNotNullWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertnotnullwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertSame`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertsamerecipe)
* [Refaster template `TestNGToAssertJRules.AssertSameWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertsamewithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertNotSame`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertnotsamerecipe)
* [Refaster template `TestNGToAssertJRules.AssertNotSameWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertnotsamewithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqual`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalrecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualFloatsWithDelta`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalfloatswithdeltarecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualFloatsWithDeltaWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalfloatswithdeltawithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualDoublesWithDelta`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequaldoubleswithdeltarecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualDoublesWithDeltaWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequaldoubleswithdeltawithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualArrayIterationOrder`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalarrayiterationorderrecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualArrayIterationOrderWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalarrayiterationorderwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualArraysIrrespectiveOfOrder`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalarraysirrespectiveoforderrecipe)
* [Refaster template `TestNGToAssertJRules.AssertEqualArraysIrrespectiveOfOrderWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertequalarraysirrespectiveoforderwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertUnequal`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertunequalrecipe)
* [Refaster template `TestNGToAssertJRules.AssertUnequalWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertunequalwithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertUnequalFloatsWithDelta`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertunequalfloatswithdeltarecipe)
* [Refaster template `TestNGToAssertJRules.AssertUnequalFloatsWithDeltaWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertunequalfloatswithdeltawithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertUnequalDoublesWithDelta`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertunequaldoubleswithdeltarecipe)
* [Refaster template `TestNGToAssertJRules.AssertUnequalDoublesWithDeltaWithMessage`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertunequaldoubleswithdeltawithmessagerecipe)
* [Refaster template `TestNGToAssertJRules.AssertThrows`](../../../../tech/picnic/errorprone/refasterrules/testngtoassertjrulesrecipes$assertthrowsrecipe)

</TabItem>

<TabItem value="yaml-recipe-list" label="Yaml Recipe List">

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes
displayName: Refaster rules that replace TestNG assertions with equivalent AssertJ assertions
description: <p>Some of the classes below have TestNG `@BeforeTemplate`s that reference wildcard type –  bounds (`<?>`), while the associated AssertJ `@AfterTemplate`s reference stricter –  type bounds. This introduces the risk of producing invalid code. We do this anyway, because –  TestNG's wildcard types can cause javac to infer less specific types than AssertJ requires, while –  the appropriate (more specific) types _will_ be inferred properly when plugged into AssertJ's –  API. –  –  <p>The following is an example of a TestNG statement, which would not be rewritten if it weren't –  for the wildcard matching (note that the type parameters of the map on the right-hand side will –  be inferred to be `<Object, Object>` rather than `<String, Object>`). –  –  <pre>{@code –  List<Map<String, Object>> myMaps = new ArrayList<>(); –  assertEquals(myMaps, ImmutableList.of(ImmutableMap.of())); –  }</pre>. [Source](https://error-prone.picnic.tech/refasterrules/TestNGToAssertJRules).
recipeList:
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$FailRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$FailWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$FailWithMessageAndThrowableRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertTrueRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertTrueWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertFalseRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertFalseWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertNullRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertNullWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertNotNullRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertNotNullWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertSameRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertSameWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertNotSameRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertNotSameWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualFloatsWithDeltaRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualFloatsWithDeltaWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualDoublesWithDeltaRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualDoublesWithDeltaWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualArrayIterationOrderRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualArrayIterationOrderWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualArraysIrrespectiveOfOrderRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertEqualArraysIrrespectiveOfOrderWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertUnequalRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertUnequalWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertUnequalFloatsWithDeltaRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertUnequalFloatsWithDeltaWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertUnequalDoublesWithDeltaRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertUnequalDoublesWithDeltaWithMessageRecipe
  - tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes$AssertThrowsRecipe

```
</TabItem>
</Tabs>

## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-third-party:0.8.0` in your build file or by running a shell command (in which case no build changes are needed): 
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:

```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.24.0")
}

rewrite {
    activeRecipe("tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes")
    exportDatatables = true
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-third-party:0.8.0")
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
        rewrite("org.openrewrite.recipe:rewrite-third-party:0.8.0")
    }
    rewrite {
        activeRecipe("tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes")
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
            <recipe>tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-third-party</artifactId>
            <version>0.8.0</version>
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
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-third-party:RELEASE -Drewrite.activeRecipes=tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes -Drewrite.exportDatatables=true
```
</TabItem>
<TabItem value="moderne-cli" label="Moderne CLI">

You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

```shell title="shell"
mod run . --recipe TestNGToAssertJRulesRecipes
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/tech.picnic.errorprone.refasterrules.TestNGToAssertJRulesRecipes">
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
