# docs

* https://docs.oracle.com/javase/8/docs/api/
* [What's New in JDK 8](http://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html)

# Collections

## Lists

### partition

```java
final List<String> list = asList("a", "ba", "aaa", "baaa", "aaa", "ba");
final Map<Boolean, List<String>> map = list.stream()
    .collect(Collectors.partitioningBy(s -> s.startsWith("a")));
assertThat(map.get(true)).contains("a", "aaa", "aaa");
assertThat(map.get(false)).contains("ba", "baaa", "ba");
```

