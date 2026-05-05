---
title: "Micronaut Framework 5.0 drops support for RxJava 2"
url: "https://micronaut.io/2026/04/30/micronaut-framework-5-0-drops-support-for-rxjava-2/"
date: "Thu, 30 Apr 2026 09:14:47 +0000"
author: "Sergio Del Amo Caballero"
feed_url: "https://micronaut.io/blog/feed/"
---
<p>Micronaut Framework 5.0, to be released in Q2 2026, drops support for RxJava 2. Micronaut 5 users have two reactive options: <a href="https://micronaut-projects.github.io/micronaut-reactor/latest/guide">Project Reactor</a> or <a href="https://micronaut-projects.github.io/micronaut-rxjava3/latest/guide">RxJava 3</a>.</p>
<p>Micronaut public APIs are reactive library–agnostic. However, internally, when a reactive library is required, we use Project Reactor.</p>
<p>If you want to migrate from RxJava 2 to RxJava 3, you need to replace the dependency <code>io.micronaut.rxjava2:micronaut-rxjava2</code> with <code>io.micronaut.rxjava3:micronaut-rxjava3</code>, and update the following imports:</p>
<ul>
<li><code>io.reactivex.Completable</code> → <code>io.reactivex.rxjava3.core.Completable</code></li>
<li><code>io.reactivex.Flowable</code> → <code>io.reactivex.rxjava3.core.Flowable</code></li>
<li><code>io.reactivex.Maybe</code> → <code>io.reactivex.rxjava3.core.Maybe</code></li>
<li><code>io.reactivex.Single</code> → <code>io.reactivex.rxjava3.core.Single</code></li>
</ul>
<p>The post <a href="https://micronaut.io/2026/04/30/micronaut-framework-5-0-drops-support-for-rxjava-2/">Micronaut Framework 5.0 drops support for RxJava 2</a> appeared first on <a href="https://micronaut.io">Micronaut Framework</a>.</p>
