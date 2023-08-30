# `PlexusFileUtils` Refaster recipes

**org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes**

_Refaster template recipes for `org.openrewrite.java.migrate.plexus.PlexusFileUtils`._

## Source

[GitHub](https://github.com/openrewrite/rewrite-migrate-java/blob/main/src/main/java/org/openrewrite/java/migrate/plexus/PlexusFileUtilsRecipes.java), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-migrate-java/2.0.10/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 2.0.10


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-migrate-java:2.0.10` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.2.4")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:2.0.10")
}
```
{% endcode %}
{% endtab %}
{% tab title="Maven POM" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.4.2</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>2.0.10</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}

{% tab title="Maven Command Line" %}
{% code title="shell" %}
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-migrate-java:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Refaster template `PlexusFileUtils.DeleteDirectoryFile`](../../../java/migrate/plexus/plexusfileutilsrecipes$deletedirectoryfilerecipe.md)
* [Refaster template `PlexusFileUtils.DeleteDirectoryString`](../../../java/migrate/plexus/plexusfileutilsrecipes$deletedirectorystringrecipe.md)
* [Refaster template `PlexusFileUtils.FileExistsString`](../../../java/migrate/plexus/plexusfileutilsrecipes$fileexistsstringrecipe.md)
* [Refaster template `PlexusFileUtils.GetFile`](../../../java/migrate/plexus/plexusfileutilsrecipes$getfilerecipe.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes
displayName: `PlexusFileUtils` Refaster recipes
description: Refaster template recipes for `org.openrewrite.java.migrate.plexus.PlexusFileUtils`.
recipeList:
  - org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes$DeleteDirectoryFileRecipe
  - org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes$DeleteDirectoryStringRecipe
  - org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes$FileExistsStringRecipe
  - org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes$GetFileRecipe

```
{% endtab %}
{% endtabs %}

## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.migrate.plexus.PlexusFileUtilsRecipes)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.