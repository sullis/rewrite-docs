# Ensure VPC subnets do not assign public IP by default

 **org.openrewrite.terraform.aws.EnsureVPCSubnetsDoNotAssignPublicIPByDefault** _Ensure VPC subnets do not assign public IP by default._

### Tags

* terraform
* AWS
* CKV\_AWS\_130

## Source

[Github](https://github.com/openrewrite/rewrite-terraform), [Issue Tracker](https://github.com/openrewrite/rewrite-terraform/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-terraform/0.5.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-terraform
* version: 0.5.0

## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-terraform:0.5.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.9.0")
}

rewrite {
    activeRecipe("org.openrewrite.terraform.aws.EnsureVPCSubnetsDoNotAssignPublicIPByDefault")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-terraform:0.5.0")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.11.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.terraform.aws.EnsureVPCSubnetsDoNotAssignPublicIPByDefault</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-terraform</artifactId>
            <version>0.5.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.terraform.aws.EnsureVPCSubnetsDoNotAssignPublicIPByDefault`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Terraform configuration](../addconfiguration.md)
  * resourceName: `aws_subnet`
  * content: `map_public_ip_on_launch = false`
{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.terraform.aws.EnsureVPCSubnetsDoNotAssignPublicIPByDefault
displayName: Ensure VPC subnets do not assign public IP by default
description: Ensure VPC subnets do not assign public IP by default.
tags:
  - terraform
  - AWS
  - CKV_AWS_130
recipeList:
  - org.openrewrite.terraform.AddConfiguration:
      resourceName: aws_subnet
      content: map_public_ip_on_launch = false
```
{% endtab %}
{% endtabs %}
