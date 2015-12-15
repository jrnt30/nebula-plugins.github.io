---
layout: toc-page
title: Getting Started
id: getting_started
lang: en
---

* Table of contents. This line is required to start the list.
{:toc}

# Getting Started

Nebula is a collection of plugins built on top of Gradle. You will need to understand how Gradle works to understand how to integrate Nebula. The team at Gradle maintains a [getting started page for Java projects](http://gradle.org/getting-started-gradle-java/).  

We publish all Nebula plugins to [Bintray](https://bintray.com/nebula/gradle-plugins), as well as the [Gradle Plugin portal](https://plugins.gradle.org/). Since we publish to the Gradle Plugin portal, including a Nebula plugin into your Gradle build is as easy as adding a single line to your `build.gradle` file:

~~~output
apply plugin: 'nebula.dependency-lock'
~~~

After including this plugin in your `build.gradle`, you will be able to take advantage of all the features it has to offer. 

# What can Nebula do for you?

To understand how Nebula can make your builds better, we have tried to categorize the Nebula plugins. To help you better understand which plugins might be useful, we've put together some common use cases.

## For organizations

Many of the Nebula plugins are useful for targeting problems that plague an organization or enterprise.

#### I want to make sure nobody in my organization builds with a particular dependency

Occasionally, Netflix engineers encounter a dependency that is considered harmful (for a variety of reasons) and needs to be removed from the overall dependency graph. We built the [gradle-resolution-rules-plugin]({{ site.baseurl }}/plugins/gradle_resolution_rules.html) as a simple approach to ensuring that we can quickly fix or fail builds based on the presence of the harmful dependency.   

Check out the [gradle-resolution-rules-plugin page]({{ site.baseurl }}/plugins/gradle_resolution_rules.html) for details on how to use it.

#### I want to make sure my library/version is always consumed with a fixed set of other library/versions

It is not uncommon for multiple libraries to be consumed as a dependency/version set in order to work properly. For instance, imagine there are three libraries: platform-core, platform-ipc and platform-cache. Consumers of the libraries should consume the same version of all three or unknown issues may arise. We built the [nebula-dependency-recommender-plugin]({{ site.baseurl }}/plugins/nebula_dependency_recommender.html) to make it easier to produce and consume [Maven BOM files](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html) to accomplish this task.

Check out the [nebula-dependency-recommender-plugin page]({{ site.baseurl }}/plugins/nebula_dependency_recommender.html) for details on how to use it.

#### I want to make sure engineers provide a mechanism to install or deploy their application

A common challenge in any organization is finding a simple, consistent way by which application developers can package and install their application for deployment. Chef, Puppet and a few other tools offer solutions to this problem. At Netflix, we decided to have application owners build OS specific packages. In order to simplify this process, we have built the [gradle-ospackage-plugin]({{ site.baseurl }}/plugins/gradle_ospackage.html).

Check out the [gradle-ospackage-plugin page]({{ site.baseurl }}/plugins/gradle_ospackage.html) for details on how to use it.

#### I want to gather metrics and data about all builds within my organization

As tools team scale the usage of an enterprise build solution, gathering metrics about the state of builds, both local and on a CI server. To accomplish this, we built the [gradle-metrics-plugin]({{ site.baseurl }}/plugins/gradle_metrics.html). This plugin will collect information about each build, and publish this data to [ElasticSearch](https://www.elastic.co/products/elasticsearch).

Check out the [gradle-metrics-plugin page]({{ site.baseurl }}/plugins/gradle_metrics.html) for details on how to use it.

#### I want to make sure all projects in my organization provide contact information

Maven provides a solution to this problem in their pom file schema, but Gradle does not. We built the [gradle-contacts-plugin]({{ site.baseurl }}/plugins/gradle_contacts.html) to allow this information to be captured inside a `build.gradle` file. 

Check out the [gradle-contacts-plugin page]({{ site.baseurl }}/plugins/gradle_contacts.html) for details on how to use it.

## For individual projects

While Nebula was built to tackle build issues at Netflix, many of the plugins are useful to standalone Java projects.

#### I want to ensure that previous versions of my code build with the exact same dependencies

In order to ensure that previous versions of your application have repeatable builds, you need to ensure that your transitive dependency graph is exactly the same. In order to do this, we created the [gradle-dependency-lock-plugin]({{ site.baseurl }}/plugins/gradle_dependency_lock.html), that will generate a `dependencies.lock` file and check that into version control. The plugin will also ensure that the locked versions are forced during a build.

Check out the [gradle-dependency-lock-plugin page]({{ site.baseurl }}/plugins/gradle_dependency_lock.html) for details on how to use it.

#### I want to use semantic versioning for my Java project

Gradle allows you to define a version number, but doesn't provide intelligence around how to easily manage a project's version. We built the [nebula-release-plugin]({{ site.baseurl }}/plugins/nebula_release.html) to allow us to manage releases of our software, using [Semantic Versioning](http://semver.org/).

Check out the [nebula-release-plugin page]({{ site.baseurl }}/plugins/nebula_release.html) for details on how to use it.

#### I want to publish my Java library to a Maven (or Ivy) repository

Recent versions of Gradle allow you to publish to a Maven or Ivy repository. Unfortunately, there is a fair amount of boilerplate required to do a simple publish. We created the [nebula-publishing-plugin]({{ site.baseurl }}/plugins/nebula_publishing.html) to address much of this boilerplate and make it easy to publish a Java library.

Check out the [nebula-publishing-plugin page]({{ site.baseurl }}/plugins/nebula_publishing.html) for details on how to use it.

#### I want to manage my Atlassian Stash project during a build

Being able to manage pull requests, branches or build statuses within Atlassian Stash. In order to simplify these tasks within a Gradle build, we built the [gradle-stash-plugin]({{ site.baseurl }}/plugins/gradle_stash.html). 

Check out the [gradle-stash-plugin page]({{ site.baseurl }}/plugins/gradle_stash.html) for details on how to use it.

#### I want all the Javadocs from my multi-module project to be aggregated

If you have a multi-module project and you would like to publish all of the javadocs as a single site or zip, then you can [gradle-aggregate-javadoc-plugin]({{ site.baseurl }}/plugins/gradle_aggregate_javadoc.html). 

Check out the [gradle-aggregate-javadoc-plugin page]({{ site.baseurl }}/plugins/gradle_aggregate_javadoc.html) for details on how to use it.

#### I want to override certain build properties from the command-line

Every once in a while, the need arises to set a value inside a Gradle build from the command line. Gradle currently does not allow you to do this. We built the [gradle-override-plugin]({{ site.baseurl }}/plugins/gradle_override.html) that will allow you to set any property in the Gradle build.

Check out the [gradle-override-plugin page]({{ site.baseurl }}/plugins/gradle_override.html) for details on how to use it.