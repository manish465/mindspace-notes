In Java, a stream is a sequence of objects that supports various methods which can be pipelined to produce the desired result.

```Java
List<Integer> number = Arrays.asList(2,3,4,5);
List<Integer> square = number.stream().map(x->x*x).collect(Collectors.toList());
```

#Java