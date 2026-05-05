---
title: "Micronaut Framework 5.0 with Java 25 baseline"
url: "https://micronaut.io/2026/04/27/micronaut-framework-5-0-with-java-25-baseline/"
date: "Mon, 27 Apr 2026 14:34:04 +0000"
author: "Sergio Del Amo Caballero"
feed_url: "https://micronaut.io/blog/feed/"
---
<p>Starting with Micronaut Framework 5.0, to be released in Q2 2026, the Java baseline will be Java 25.</p>
<h2>Use modern Java features</h2>
<p>By setting a Java 25 baseline, we can improve our internal code and public APIs by continuing to use features such as <a href="https://openjdk.org/jeps/444">Virtual Threads</a>, <a href="https://openjdk.org/jeps/453">Structured Concurrency</a>, <a href="https://openjdk.org/jeps/506">Scoped Values</a>, <a href="https://openjdk.org/jeps/441">Pattern Matching for switch</a>, <a href="https://openjdk.org/jeps/440">Record Patterns</a>, and <a href="https://openjdk.org/jeps/430">String Templates</a>.<br />
For example, Micronaut Framework 5.0 provides an alternative implementation of context propagation that uses <a href="https://openjdk.org/jeps/506">Scoped Values</a>, in addition to the default implementation based on thread-local variables.</p>
<h2>Cloud vendors ready for Java 25</h2>
<p>Many Micronaut users deploy to the cloud, and cloud vendors are preparing for Java 25. For example, <a href="https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html">AWS Lambda runtimes</a>, <a href="https://docs.aws.amazon.com/elasticbeanstalk/latest/platforms/platforms-supported.html#platforms-supported.javase">AWS Elastic Beanstalk</a>, and <a href="https://cloud.google.com/functions/docs/concepts/execution-environment#runtimes">Google Cloud Functions</a>.<br />
We are confident that <a href="https://learn.microsoft.com/en-us/azure/azure-functions/functions-reference-java?tabs=bash%2Cconsumption#supported-versions">Azure Functions</a> and <a href="https://docs.oracle.com/en-us/iaas/Content/Functions/Tasks/languagessupportedbyfunctions.htm">OCI (Oracle Cloud Infrastructure) Functions</a><br />
will soon support Java 25.</p>
<h2>Show modern code in our documentation</h2>
<p><a href="https://guides.micronaut.io/">Micronaut Guides</a> and <a href="https://docs.micronaut.io/">Micronaut module documentation</a> embed code samples from real applications.<br />
By setting a Java 25 baseline, we can update those samples to use modern Java features, making the language more appealing and improving the developer experience.</p>
<h2>Performance improvements</h2>
<p><a href="https://inside.java/2025/10/20/jdk-25-performance-improvements/">Java 25 brings performance improvements</a>. By building and releasing artifacts with a baseline of Java 25, Micronaut users can benefit from these improvements when upgrading to the latest framework version.</p>
<h2>Reduce CI build times</h2>
<p>Micronaut Framework 4.0 continuous integration tests run against a matrix of Java versions: 17, 21, and 25.</p>
<p>Our Java 25 builds are already significantly faster. By dropping support for older Java versions in Micronaut Framework 5.0, we can build and test modules more quickly and deliver features faster to the Micronaut community.</p>
<h2>A message to the Java community</h2>
<p>The Java community should embrace Java 25. As framework developers, we should take a clear position. It is time to move forward. Your applications will run faster, and your development experience will improve.</p>
<h2>How to continue using Java 17 or 21 with the Micronaut Framework?</h2>
<p>If you need to use an older version, Micronaut Framework 4.x will continue to support Java 17 and Java 21.</p>
<p>The post <a href="https://micronaut.io/2026/04/27/micronaut-framework-5-0-with-java-25-baseline/">Micronaut Framework 5.0 with Java 25 baseline</a> appeared first on <a href="https://micronaut.io">Micronaut Framework</a>.</p>
