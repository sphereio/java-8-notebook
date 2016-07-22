# docs

* https://docs.oracle.com/javase/8/docs/api/
* [What's New in JDK 8](http://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html)

# Optional
* http://winterbe.com/posts/2015/03/15/avoid-null-checks-in-java/

# Collections and Streams

## Streams

### Stream of Stream

```java
final Stream<Stream<String>> streamStream = createStreameSomeHow();
final List<String> result = streamStream
        .reduce(Stream.empty(), Stream::concat)
        .collect(toList());
```

## Lists

### partition

```java
final List<String> list = asList("a", "ba", "aaa", "baaa", "aaa", "ba");
final Map<Boolean, List<String>> map = list.stream()
    .collect(Collectors.partitioningBy(s -> s.startsWith("a")));
assertThat(map.get(true)).contains("a", "aaa", "aaa");
assertThat(map.get(false)).contains("ba", "baaa", "ba");
```

# Lambda Functions and closures
## Weird stuff

```java
final Predicate<String> predicate = "GET"::equals;
```

# CompletableFuture and CompletionStage

* http://www.jesperdj.com/2015/09/26/the-future-is-completable-in-java-8/

# Articles
* http://www.javacodegeeks.com/2015/05/constructors-must-be-code-free.html
* http://www.yegor256.com/2015/02/26/composable-decorators.html
* http://www.javacodegeeks.com/2014/09/objects-should-be-immutable.html
