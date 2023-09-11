# Migrate to Spring Security 6.1

**org.openrewrite.java.spring.security6.UpgradeSpringSecurity\_6\_1**

_Migrate applications to the latest Spring Security 6.1 release. This recipe will modify an application's build files, make changes to deprecated/preferred APIs, and migrate configuration settings that have changes between versions._

### Tags

* spring
* security

## Source

[GitHub](https://github.com/openrewrite/rewrite-spring/blob/main/src/main/resources/META-INF/rewrite/spring-security-61.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-spring/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-spring/5.0.9/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-spring
* version: 5.0.9


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-spring:5.0.9` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.3.5")
}

rewrite {
    activeRecipe("org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_1")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-spring:5.0.9")
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
        <version>5.5.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_1</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-spring</artifactId>
            <version>5.0.9</version>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-spring:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_1
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Migrate to Spring Security 6.0](../../../java/spring/security6/upgradespringsecurity_6_0.md)
* [Upgrade Gradle or Maven dependency versions](../../../java/dependencies/upgradedependencyversion.md)
  * groupId: `org.springframework.security`
  * artifactId: `*`
  * newVersion: `6.1.x`
  * overrideManagedVersion: `false`
* [Convert `HttpSecurity` chained calls into Lambda DSL](../../../java/spring/boot2/httpsecuritylambdadsl.md)
* [Convert `ServerHttpSecurity` chained calls into Lambda DSL](../../../java/spring/boot2/serverhttpsecuritylambdadsl.md)
* [Convert `HeadersConfigurer` chained calls into Lambda DSL](../../../java/spring/boot2/headersconfigurerlambdadsl.md)
* [Convert `OAuth2LoginConfigurer` chained calls into Lambda DSL](../../../java/spring/security6/oauth2/client/oauth2loginlambdadsl.md)
* [Convert `OAuth2ClientConfigurer` chained calls into Lambda DSL](../../../java/spring/security6/oauth2/client/oauth2clientlambdadsl.md)
* [Convert `OAuth2ResourceServerConfigurer` chained calls into Lambda DSL](../../../java/spring/security6/oauth2/server/resource/oauth2resourceserverlambdadsl.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_1
displayName: Migrate to Spring Security 6.1
description: Migrate applications to the latest Spring Security 6.1 release. This recipe will modify an application's build files, make changes to deprecated/preferred APIs, and migrate configuration settings that have changes between versions.

tags:
  - spring
  - security
recipeList:
  - org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_0
  - org.openrewrite.java.dependencies.UpgradeDependencyVersion:
      groupId: org.springframework.security
      artifactId: *
      newVersion: 6.1.x
      overrideManagedVersion: false
  - org.openrewrite.java.spring.boot2.HttpSecurityLambdaDsl
  - org.openrewrite.java.spring.boot2.ServerHttpSecurityLambdaDsl
  - org.openrewrite.java.spring.boot2.HeadersConfigurerLambdaDsl
  - org.openrewrite.java.spring.security6.oauth2.client.OAuth2LoginLambdaDsl
  - org.openrewrite.java.spring.security6.oauth2.client.OAuth2ClientLambdaDsl
  - org.openrewrite.java.spring.security6.oauth2.server.resource.OAuth2ResourceServerLambdaDsl

```
{% endtab %}
{% endtabs %}

## Contributors
* [Knut Wannheden](mailto:knut@moderne.io)
* [Alex Boyko](mailto:aboyko@vmware.com)
* Kun Li
* [Shannon Pamperl](mailto:shanman190@gmail.com)
* [Kun Li](mailto:kun@moderne.io)
* [Nick McKinney](mailto:mckinneynicholas@gmail.com)
* [Tim te Beek](mailto:tim@moderne.io)
* [Johannes Jank](mailto:johannes.wengert@googlemail.com)
* [Jonathan Schnéider](mailto:jkschneider@gmail.com)
* [Sam Snyder](mailto:sam@moderne.io)
* Patrick Way
* [Nick McKinney](mailto:mckinneynichoals@gmail.com)
* [Patrick](mailto:patway99@gmail.com)
* Josh Soref
* [Simon Verhoeven](mailto:verhoeven.simon@gmail.com)


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.spring.security6.UpgradeSpringSecurity_6_1)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.