---
published: true
---
## Sync, Async, Blocking, and Non-Blocking

### 관점의 문제이다.

- Sync, Async:
  - 처리되는 방식. 비동기는 callback 으로 받아서 처리...
- Blocking, Non-Blocking:
  - 호출하는 함수가 완료여부 상관없이 바로 return 해줄때 non-blocking.
  - 완료할때까지 기다려야 하면 blocking.



![관계를 나타내는 이미지]({{site.baseurl}}/_posts/2020/2020-12-30/2020-12-30-sync-async-blocking-non-blocking-1.jpg)
관계를 나타내는 이미지(이미지를 봐도 이해안되네?)

---

### 명백한 2가지 케이스
1. sync + blocking:
  - 말그대로 순차적 실행
1. async + non-blocking: 
  - 흔히 말하는 "async" 로 실행했다는 의미

### 한번더 생각하게 하는 2가지 케이스
1. sync + non-blocking:
  - 순차실행인데 호출한 함수가 non-blocking 이라서 바로 return 해줬다. 고맙긴 한데 종료되었는지 확인하려면 재차 물어봐야 함. isDone 계속 물어보는 케이스가 비슷할듯.
  
```java
    ExecutorService executor = Executors.newFixedThreadPool(1);
    Future<Integer> future = executor.submit(task);

    while (!future.isDone()) {
      System.out.println("Still working on it....");
      Thread.sleep(100);
    }
    System.out.println("The Job is done.");		
```

1. async + blocking: 
  - async 로 호출하였는데 blocking 에 걸려서, sync+blocking 같은 결과가 나옴.
