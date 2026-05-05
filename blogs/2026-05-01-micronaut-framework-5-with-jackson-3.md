---
title: "Micronaut framework 5 with Jackson 3"
url: "https://micronaut.io/2026/05/01/micronaut-framework-5-with-jackson-3/"
date: "Fri, 01 May 2026 09:59:08 +0000"
author: "Sergio Del Amo Caballero"
feed_url: "https://micronaut.io/blog/feed/"
---
<p>Since <a href="https://micronaut.io/2022/01/27/micronaut-framework-3-3-released/">Micronaut Framework 3.3.0</a>, you can use <a href="https://micronaut-projects.github.io/micronaut-serialization/latest/guide/">Micronaut Serialization</a> as an alternative to <a href="https://docs.micronaut.io/latest/guide/#serializationUsingJacksonDatabind">Micronaut Jackson Databind</a>. Moreover, the framework exposes low-level APIs such as <a href="https://docs.micronaut.io/latest/api/io/micronaut/json/JsonMapper.html">JsonMapper</a> to avoid coupling between serialization implementations.</p>
<p>Micronaut Jackson Databind internally used Jackson 2. With the release of Micronaut 5, Micronaut Jackson Databind (<code>micronaut-jackson-databind</code>) uses Jackson 3. See the <a href="https://github.com/FasterXML/jackson/blob/main/jackson3/MIGRATING_TO_JACKSON_3.md">Jackson 3 upgrade guide</a> and the <a href="https://github.com/FasterXML/jackson/wiki/Jackson-Release-3.0">Jackson 3 release notes</a>.</p>
<p>To update your application, you can use the <a href="https://docs.openrewrite.org/recipes/java/jackson/upgradejackson_2_3" rel="nofollow">Jackson 2 to Jackson 3 OpenRewrite recipe</a>.</p>
<div class="highlight highlight-source-kotlin notranslate position-relative overflow-auto">
<pre>plugins {
    ..
    id("org.openrewrite.rewrite")
}
repositories {
    mavenCentral()
}
rewrite {
    activeRecipe("org.openrewrite.java.jackson.UpgradeJackson_2_3")
}
dependencies {
    rewrite("org.openrewrite.recipe:rewrite-jackson:1.11.0")
    compileOnly("tools.jackson.core:jackson-databind:2.17.2")
}</pre>
</div>
<div>Alternatively, apply the following changes to your project:</div>
<ul>
<li>Replace <code>com.fasterxml.jackson.databind.annotation.JsonDeserialize</code> with <code>tools.jackson.databind.annotation.JsonDeserialize</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.annotation.JsonPOJOBuilder</code> with <code>tools.jackson.databind.annotation.JsonPOJOBuilder</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.JsonNode</code> with <code>tools.jackson.databind.JsonNode</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.node.JsonNodeFactory</code> with <code>tools.jackson.databind.node.JsonNodeFactory</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.node.ObjectNode</code> with <code>tools.jackson.databind.node.ObjectNode</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.ObjectMapper</code> with <code>tools.jackson.databind.ObjectMapper</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.PropertyNamingStrategies</code> with <code>tools.jackson.databind.PropertyNamingStrategies</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.JsonParser</code> with <code>tools.jackson.core.JsonParser</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.JsonToken</code> with <code>tools.jackson.core.JsonToken</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.JsonFactory</code> with <code>tools.jackson.core.json.JsonFactory</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.StreamWriteFeature</code> with <code>tools.jackson.core.StreamWriteFeature</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.json.JsonReadFeature</code> with <code>tools.jackson.core.json.JsonReadFeature</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.json.JsonWriteFeature</code> with <code>tools.jackson.core.json.JsonWriteFeature</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.JsonFactoryBuilder</code> with <code>tools.jackson.core.json.JsonFactoryBuilder</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.ser.impl.SimpleFilterProvider</code> with <code>tools.jackson.databind.ser.std.SimpleFilterProvider</code>.</li>
<li>Replace <code>com.fasterxml.jackson.core.JsonGenerator</code> with <code>tools.jackson.core.JsonGenerator</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.jsonFormatVisitors.JsonObjectFormatVisitor</code> with <code>tools.jackson.databind.jsonFormatVisitors.JsonObjectFormatVisitor</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.ser.BeanPropertyWriter</code> with <code>tools.jackson.databind.ser.BeanPropertyWriter</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.ser.PropertyFilter</code> with <code>tools.jackson.databind.ser.PropertyFilter</code>.</li>
<li>Replace <code>com.fasterxml.jackson.databind.ser.PropertyWriter</code> with <code>tools.jackson.databind.ser.PropertyWriter</code>.</li>
</ul>
<p><strong>Exceptions</strong></p>
<ul>
<li>Some instances of <code>com.fasterxml.jackson.core.JsonParseException</code> are now <code>tools.jackson.core.JacksonException</code>.</li>
<li><code>com.fasterxml.jackson.databind.JsonMappingException</code> (the root for databind exceptions) becomes <code>tools.jackson.databind.DatabindException</code>.</li>
<li><code>com.fasterxml.jackson.core.JsonProcessingException</code> becomes <code>tools.jackson.core.JacksonException</code>.</li>
<li><code>com.fasterxml.jackson.databind.exc.InvalidFormatException</code> becomes <code>tools.jackson.databind.exc.InvalidFormatException</code>.</li>
</ul>
<p>Some internal Micronaut Jackson classes have been relocated:</p>
<ul>
<li><code>io.micronaut.jackson.env.JsonPropertySourceLoader</code> → <code>io.micronaut.jackson.core.env.JsonPropertySourceLoader</code></li>
</ul>
<p>The post <a href="https://micronaut.io/2026/05/01/micronaut-framework-5-with-jackson-3/">Micronaut framework 5 with Jackson 3</a> appeared first on <a href="https://micronaut.io">Micronaut Framework</a>.</p>
