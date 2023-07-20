# Update Maven wrapper

**org.openrewrite.maven.UpdateMavenWrapper**

_Update the version of Maven used in an existing Maven wrapper._

## Source

[GitHub](https://github.com/openrewrite/rewrite/blob/main/rewrite-maven/src/main/java/org/openrewrite/maven/UpdateMavenWrapper.java), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite/rewrite-maven/8.1.11/jar)

* groupId: org.openrewrite
* artifactId: rewrite-maven
* version: 8.1.11

## Options

| Type | Name | Description |
| -- | -- | -- |
| `String` | wrapperVersion | *Optional*. An exact version number or node-style semver selector used to select the wrapper version number. |
                        | `String` | wrapperDistribution | *Optional*. The distribution of the Maven wrapper to use.

* "bin" uses a `maven-wrapper.jar` compiled binary.
* "only-script" uses a lite version of `mvnw`/`mvnw.cmd` using wget/curl or powershell. (required wrapper 3.2.0 or newer)
* "script" downloads `maven-wrapper.jar` or `MavenWrapperDownloader.java` to then download a full distribution.
* "source" uses `MavenWrapperDownloader.java` source file.

Defaults to "bin". |
| `String` | distributionVersion | *Optional*. An exact version number or node-style semver selector used to select the Maven version number. |
| `String` | repositoryUrl | *Optional*. The URL of the repository to download the Maven wrapper and distribution from. Supports repositories with a Maven layout. Defaults to `https://repo.maven.apache.org/maven2`. |
| `Boolean` | addIfMissing | *Optional*. Add a Maven wrapper, if it's missing. Defaults to `true`. |


## Usage

This recipe has no required configuration parameters and comes from a rewrite core library. It can be activated directly without adding any dependencies.
{% tabs %}

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
            <recipe>org.openrewrite.maven.UpdateMavenWrapper</recipe>
          </activeRecipes>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}

{% tab title="Maven Command Line" %}
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.
{% code title="shell" %}
```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run \
  -Drewrite.activeRecipes=org.openrewrite.maven.UpdateMavenWrapper
```
{% endcode %}
{% endtab %}
{% endtabs %}

## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.maven.UpdateMavenWrapper)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.