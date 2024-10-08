---
sidebar_label: "Recommended ESLint Styling"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Recommended ESLint Styling

**org.openrewrite.codemods.format.RecommendedESLintStyling**

_Collection of stylistic ESLint rules that are recommended by the [ESLint Style.](https://eslint.style/)_

### Tags

* eslint
* stylistic

## Recipe source

[GitHub](https://github.com/openrewrite/rewrite-codemods/blob/main/src/main/resources/META-INF/rewrite/stylistic.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-codemods/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-codemods/0.3.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-codemods
* version: 0.3.0


## Definition

<Tabs groupId="recipeType">
<TabItem value="recipe-list" label="Recipe List" >
* [Lint source code with ESLint](../../codemods/eslint)
  * fix: `true`
  * configFile: `{   "root": true,   "parser": "@typescript-eslint/parser",   "parserOptions": { "project": ["./tsconfig.json"] },   "plugins": ["@stylistic"],   "rules": {     "@stylistic/array-bracket-newline": 2,     "@stylistic/array-bracket-spacing": 2,     "@stylistic/array-element-newline": 2,     "@stylistic/arrow-parens": 2,     "@stylistic/arrow-spacing": 2,     "@stylistic/block-spacing": 2,     "@stylistic/brace-style": 2,     "@stylistic/comma-dangle": 2,     "@stylistic/comma-spacing": 2,     "@stylistic/comma-style": 2,     "@stylistic/computed-property-spacing": 2,     "@stylistic/dot-location": 2,     "@stylistic/eol-last": 2,     "@stylistic/func-call-spacing": 2,     "@stylistic/function-call-argument-newline": 2,     "@stylistic/function-call-spacing": 2,     "@stylistic/function-paren-newline": 2,     "@stylistic/generator-star-spacing": 2,     "@stylistic/implicit-arrow-linebreak": 2,     "@stylistic/indent": 2,     "@stylistic/indent-binary-ops": 2,     "@stylistic/jsx-closing-bracket-location": 2,     "@stylistic/jsx-closing-tag-location": 2,     "@stylistic/jsx-curly-brace-presence": 2,     "@stylistic/jsx-curly-newline": 2,     "@stylistic/jsx-curly-spacing": 2,     "@stylistic/jsx-equals-spacing": 2,     "@stylistic/jsx-first-prop-new-line": 2,     "@stylistic/jsx-indent": 2,     "@stylistic/jsx-indent-props": 2,     "@stylistic/jsx-max-props-per-line": 2,     "@stylistic/jsx-newline": 2,     "@stylistic/jsx-one-expression-per-line": 2,     "@stylistic/jsx-pascal-case": 2,     "@stylistic/jsx-props-no-multi-spaces": 2,     "@stylistic/jsx-quotes": 2,     "@stylistic/jsx-self-closing-comp": 2,     "@stylistic/jsx-sort-props": 2,     "@stylistic/jsx-tag-spacing": 2,     "@stylistic/jsx-wrap-multilines": 2,     "@stylistic/key-spacing": 2,     "@stylistic/keyword-spacing": 2,     "@stylistic/linebreak-style": 2,     "@stylistic/lines-around-comment": 2,     "@stylistic/lines-between-class-members": 2,     "@stylistic/member-delimiter-style": 2,     "@stylistic/multiline-ternary": 2,     "@stylistic/new-parens": 2,     "@stylistic/newline-per-chained-call": 2,     "@stylistic/no-confusing-arrow": 2,     "@stylistic/no-extra-parens": 2,     "@stylistic/no-extra-semi": 2,     "@stylistic/no-floating-decimal": 2,     "@stylistic/no-multi-spaces": 2,     "@stylistic/no-multiple-empty-lines": 2,     "@stylistic/no-trailing-spaces": 2,     "@stylistic/no-whitespace-before-property": 2,     "@stylistic/nonblock-statement-body-position": 2,     "@stylistic/object-curly-newline": 2,     "@stylistic/object-curly-spacing": 2,     "@stylistic/object-property-newline": 2,     "@stylistic/one-var-declaration-per-line": 2,     "@stylistic/operator-linebreak": 2,     "@stylistic/padded-blocks": 2,     "@stylistic/padding-line-between-statements": 2,     "@stylistic/quote-props": 2,     "@stylistic/quotes": 2,     "@stylistic/rest-spread-spacing": 2,     "@stylistic/semi": 2,     "@stylistic/semi-spacing": 2,     "@stylistic/semi-style": 2,     "@stylistic/space-before-blocks": 2,     "@stylistic/space-before-function-paren": 2,     "@stylistic/space-in-parens": 2,     "@stylistic/space-infix-ops": 2,     "@stylistic/space-unary-ops": 2,     "@stylistic/spaced-comment": 2,     "@stylistic/switch-colon-spacing": 2,     "@stylistic/template-curly-spacing": 2,     "@stylistic/template-tag-spacing": 2,     "@stylistic/type-annotation-spacing": 2,     "@stylistic/type-generic-spacing": 2,     "@stylistic/type-named-tuple-spacing": 2,     "@stylistic/wrap-iife": 2,     "@stylistic/wrap-regex": 2,     "@stylistic/yield-star-spacing": 2,   },   "globals": {     "browser": true,     "node": true   } } `

</TabItem>

<TabItem value="yaml-recipe-list" label="Yaml Recipe List">

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.codemods.format.RecommendedESLintStyling
displayName: Recommended ESLint Styling
description: Collection of stylistic ESLint rules that are recommended by the [ESLint Style.](https://eslint.style/) – 
tags:
  - eslint
  - stylistic
recipeList:
  - org.openrewrite.codemods.ESLint:
      fix: true
      configFile: {
  "root": true,
  "parser": "@typescript-eslint/parser",
  "parserOptions": { "project": ["./tsconfig.json"] },
  "plugins": ["@stylistic"],
  "rules": {
    "@stylistic/array-bracket-newline": 2,
    "@stylistic/array-bracket-spacing": 2,
    "@stylistic/array-element-newline": 2,
    "@stylistic/arrow-parens": 2,
    "@stylistic/arrow-spacing": 2,
    "@stylistic/block-spacing": 2,
    "@stylistic/brace-style": 2,
    "@stylistic/comma-dangle": 2,
    "@stylistic/comma-spacing": 2,
    "@stylistic/comma-style": 2,
    "@stylistic/computed-property-spacing": 2,
    "@stylistic/dot-location": 2,
    "@stylistic/eol-last": 2,
    "@stylistic/func-call-spacing": 2,
    "@stylistic/function-call-argument-newline": 2,
    "@stylistic/function-call-spacing": 2,
    "@stylistic/function-paren-newline": 2,
    "@stylistic/generator-star-spacing": 2,
    "@stylistic/implicit-arrow-linebreak": 2,
    "@stylistic/indent": 2,
    "@stylistic/indent-binary-ops": 2,
    "@stylistic/jsx-closing-bracket-location": 2,
    "@stylistic/jsx-closing-tag-location": 2,
    "@stylistic/jsx-curly-brace-presence": 2,
    "@stylistic/jsx-curly-newline": 2,
    "@stylistic/jsx-curly-spacing": 2,
    "@stylistic/jsx-equals-spacing": 2,
    "@stylistic/jsx-first-prop-new-line": 2,
    "@stylistic/jsx-indent": 2,
    "@stylistic/jsx-indent-props": 2,
    "@stylistic/jsx-max-props-per-line": 2,
    "@stylistic/jsx-newline": 2,
    "@stylistic/jsx-one-expression-per-line": 2,
    "@stylistic/jsx-pascal-case": 2,
    "@stylistic/jsx-props-no-multi-spaces": 2,
    "@stylistic/jsx-quotes": 2,
    "@stylistic/jsx-self-closing-comp": 2,
    "@stylistic/jsx-sort-props": 2,
    "@stylistic/jsx-tag-spacing": 2,
    "@stylistic/jsx-wrap-multilines": 2,
    "@stylistic/key-spacing": 2,
    "@stylistic/keyword-spacing": 2,
    "@stylistic/linebreak-style": 2,
    "@stylistic/lines-around-comment": 2,
    "@stylistic/lines-between-class-members": 2,
    "@stylistic/member-delimiter-style": 2,
    "@stylistic/multiline-ternary": 2,
    "@stylistic/new-parens": 2,
    "@stylistic/newline-per-chained-call": 2,
    "@stylistic/no-confusing-arrow": 2,
    "@stylistic/no-extra-parens": 2,
    "@stylistic/no-extra-semi": 2,
    "@stylistic/no-floating-decimal": 2,
    "@stylistic/no-multi-spaces": 2,
    "@stylistic/no-multiple-empty-lines": 2,
    "@stylistic/no-trailing-spaces": 2,
    "@stylistic/no-whitespace-before-property": 2,
    "@stylistic/nonblock-statement-body-position": 2,
    "@stylistic/object-curly-newline": 2,
    "@stylistic/object-curly-spacing": 2,
    "@stylistic/object-property-newline": 2,
    "@stylistic/one-var-declaration-per-line": 2,
    "@stylistic/operator-linebreak": 2,
    "@stylistic/padded-blocks": 2,
    "@stylistic/padding-line-between-statements": 2,
    "@stylistic/quote-props": 2,
    "@stylistic/quotes": 2,
    "@stylistic/rest-spread-spacing": 2,
    "@stylistic/semi": 2,
    "@stylistic/semi-spacing": 2,
    "@stylistic/semi-style": 2,
    "@stylistic/space-before-blocks": 2,
    "@stylistic/space-before-function-paren": 2,
    "@stylistic/space-in-parens": 2,
    "@stylistic/space-infix-ops": 2,
    "@stylistic/space-unary-ops": 2,
    "@stylistic/spaced-comment": 2,
    "@stylistic/switch-colon-spacing": 2,
    "@stylistic/template-curly-spacing": 2,
    "@stylistic/template-tag-spacing": 2,
    "@stylistic/type-annotation-spacing": 2,
    "@stylistic/type-generic-spacing": 2,
    "@stylistic/type-named-tuple-spacing": 2,
    "@stylistic/wrap-iife": 2,
    "@stylistic/wrap-regex": 2,
    "@stylistic/yield-star-spacing": 2,
  },
  "globals": {
    "browser": true,
    "node": true
  }
}


```
</TabItem>
</Tabs>

## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-codemods:0.3.0` in your build file or by running a shell command (in which case no build changes are needed): 
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:

```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.24.0")
}

rewrite {
    activeRecipe("org.openrewrite.codemods.format.RecommendedESLintStyling")
    exportDatatables = true
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-codemods:0.3.0")
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
        rewrite("org.openrewrite.recipe:rewrite-codemods:0.3.0")
    }
    rewrite {
        activeRecipe("org.openrewrite.codemods.format.RecommendedESLintStyling")
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
            <recipe>org.openrewrite.codemods.format.RecommendedESLintStyling</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-codemods</artifactId>
            <version>0.3.0</version>
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
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-codemods:RELEASE -Drewrite.activeRecipes=org.openrewrite.codemods.format.RecommendedESLintStyling -Drewrite.exportDatatables=true
```
</TabItem>
<TabItem value="moderne-cli" label="Moderne CLI">

You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

```shell title="shell"
mod run . --recipe RecommendedESLintStyling
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/org.openrewrite.codemods.format.RecommendedESLintStyling">
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
