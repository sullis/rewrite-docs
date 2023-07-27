# Update the version of core annotation processors

**org.openrewrite.java.micronaut.UpdateMavenAnnotationProcessors**

_This recipe will update the version of Maven-configured annotation processors from Micronaut Core._

## Source

[GitHub](https://github.com/openrewrite/rewrite-micronaut/blob/main/src/main/resources/META-INF/rewrite/micronaut3-to-4.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-micronaut/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-micronaut/2.1.1/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-micronaut
* version: 2.1.1


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-micronaut:2.1.1` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.1.19")
}

rewrite {
    activeRecipe("org.openrewrite.java.micronaut.UpdateMavenAnnotationProcessors")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-micronaut:2.1.1")
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
        <version>5.3.2</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.micronaut.UpdateMavenAnnotationProcessors</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-micronaut</artifactId>
            <version>2.1.1</version>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-micronaut:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.java.micronaut.UpdateMavenAnnotationProcessors
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change Maven annotation processor path](../../java/micronaut/changeannotationprocessorpath.md)
  * oldGroupId: `io.micronaut`
  * oldArtifactId: `micronaut-inject-java`
  * newVersion: `micronaut.core.version`
* [Change Maven annotation processor path](../../java/micronaut/changeannotationprocessorpath.md)
  * oldGroupId: `io.micronaut`
  * oldArtifactId: `micronaut-http-validation`
  * newVersion: `micronaut.core.version`
* [Change Maven annotation processor path](../../java/micronaut/changeannotationprocessorpath.md)
  * oldGroupId: `io.micronaut`
  * oldArtifactId: `micronaut-graal`
  * newVersion: `micronaut.core.version`
* [Change Maven annotation processor path](../../java/micronaut/changeannotationprocessorpath.md)
  * oldGroupId: `io.micronaut.*`
  * oldArtifactId: `micronaut-*`
  * exclusions: `[io.micronaut:micronaut-inject]`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.micronaut.UpdateMavenAnnotationProcessors
displayName: Update the version of core annotation processors
description: This recipe will update the version of Maven-configured annotation processors from Micronaut Core.
recipeList:
  - org.openrewrite.java.micronaut.ChangeAnnotationProcessorPath:
      oldGroupId: io.micronaut
      oldArtifactId: micronaut-inject-java
      newVersion: micronaut.core.version
  - org.openrewrite.java.micronaut.ChangeAnnotationProcessorPath:
      oldGroupId: io.micronaut
      oldArtifactId: micronaut-http-validation
      newVersion: micronaut.core.version
  - org.openrewrite.java.micronaut.ChangeAnnotationProcessorPath:
      oldGroupId: io.micronaut
      oldArtifactId: micronaut-graal
      newVersion: micronaut.core.version
  - org.openrewrite.java.micronaut.ChangeAnnotationProcessorPath:
      oldGroupId: io.micronaut.*
      oldArtifactId: micronaut-*
      exclusions: [io.micronaut:micronaut-inject]

```
{% endtab %}
{% endtabs %}

## Contributors
* [Jeremy Grelle](mailto:grellej@unityfoundation.io)


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.micronaut.UpdateMavenAnnotationProcessors)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.