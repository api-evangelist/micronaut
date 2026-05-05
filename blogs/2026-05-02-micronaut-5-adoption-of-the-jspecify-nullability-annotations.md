---
title: "Micronaut 5 adoption of the JSpecify nullability annotations"
url: "https://micronaut.io/2026/05/02/micronaut-5-adoption-of-the-jspecify-nullability-annotations/"
date: "Sat, 02 May 2026 06:53:14 +0000"
author: "Sergio Del Amo Caballero"
feed_url: "https://micronaut.io/blog/feed/"
---
<p><a href="https://jspecify.dev">JSpecify</a> nullability annotations have emerged as the standard way to define nullability constraints in Java APIs using annotations. We have migrated Micronaut’s internal APIs to use JSpecify nullability annotations.</p>
<p>If you were using Micronaut nullability annotations, replace usages of <code>io.micronaut.core.annotation.Nullable</code> with <code>org.jspecify.annotations.Nullable</code>, and usages of <code>io.micronaut.core.annotation.NonNull</code> with <code>org.jspecify.annotations.NonNull</code>.</p>
<div class="markdown-heading">
<h3 class="heading-element">Fully Qualified Types</h3>
</div>
<p>When specifying a fully qualified type, with Micronaut nullability annotations you could write:</p>
<div class="highlight highlight-source-java notranslate position-relative overflow-auto">
<pre><span class="pl-k">public</span> <span class="pl-smi">ReadBuffer</span> <span class="pl-en">adapt</span>(<span class="pl-c1">@</span><span class="pl-c1">NonNull</span> <span class="pl-smi">io</span>.<span class="pl-smi">micronaut</span>.<span class="pl-smi">core</span>.<span class="pl-smi">io</span>.<span class="pl-smi">buffer</span>.<span class="pl-smi">ByteBuffer</span>&lt;?&gt; <span class="pl-s1">buffer</span>) {</pre>
</div>
<p>With JSpecify, you need to write:</p>
<div class="highlight highlight-source-java notranslate position-relative overflow-auto">
<pre><span class="pl-k">public</span> <span class="pl-smi">ReadBuffer</span> <span class="pl-en">adapt</span>(<span class="pl-smi">io</span>.<span class="pl-smi">micronaut</span>.<span class="pl-smi">core</span>.<span class="pl-smi">io</span>.<span class="pl-smi">buffer</span>.<span class="pl-c1">@</span><span class="pl-c1">NonNull</span> <span class="pl-smi">ByteBuffer</span>&lt;?&gt; <span class="pl-s1">buffer</span>) {</pre>
</div>
<p><strong>Inner classes</strong></p>
<p>For inner classes, with Micronaut annotations you could write:</p>
<div class="highlight highlight-source-java notranslate position-relative overflow-auto">
<pre><span class="pl-k">public</span> <span class="pl-smi">FileChangedEvent</span>(<span class="pl-c1">@</span><span class="pl-c1">NonNull</span> <span class="pl-smi">Path</span> <span class="pl-s1">path</span>, <span class="pl-c1">@</span><span class="pl-c1">NonNull</span> <span class="pl-smi">WatchEvent</span>.<span class="pl-smi">Kind</span> <span class="pl-s1">eventType</span>) {</pre>
</div>
<p>With JSpecify, you need to write:</p>
<div class="highlight highlight-source-java notranslate position-relative overflow-auto">
<pre><span class="pl-k">public</span> <span class="pl-smi">FileChangedEvent</span>(<span class="pl-c1">@</span><span class="pl-c1">NonNull</span> <span class="pl-smi">Path</span> <span class="pl-s1">path</span>, <span class="pl-smi">WatchEvent</span>.<span class="pl-c1">@</span><span class="pl-c1">NonNull</span> <span class="pl-smi">Kind</span> <span class="pl-s1">eventType</span>) {</pre>
</div>
<p>Read more about the <a href="https://docs.micronaut.io/snapshot/guide/#jspecify">JSpecify Micronaut integration</a>.</p>
<p>The post <a href="https://micronaut.io/2026/05/02/micronaut-5-adoption-of-the-jspecify-nullability-annotations/">Micronaut 5 adoption of the JSpecify nullability annotations</a> appeared first on <a href="https://micronaut.io">Micronaut Framework</a>.</p>
