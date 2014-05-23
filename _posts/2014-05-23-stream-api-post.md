---
layout: post
title: StreamAPI Java 8
description: "Stream API in Java 8"
category: articles
tags: [StreamAPI, Java8, urlparameter]
comments: true
share: true
---

Java 8 is realy cool!

the folowing code parses a query string like "color=red&size=M&name=jdk8" and puts into s hashmap.

{% highlight java %}
    public QueryString(String q) {
        keyValues = Arrays.stream(q.split("&"))    // create a stream from the array produced by split
                .map(s -> s.split("="))            // map each element into an array of key value pairs around '='
                .filter(pair -> pair.length == 2)  // filter the invalid pairs 
                .collect(Collectors.toMap(pair -> pair[0], pair -> pair[1])); // collect them to a map
    }
{% endhighlight %}



See the whole code here: [tdd-examples](https://github.com/kia/tdd-examples/blob/master/src/main/java/urlqueryparser/QueryString.java)
