---
published: true
toc: true
categories:
  - Algorithm
tags:
  - Algorithm
---
## Array 형태의 Integer 덧셈
> Integer 원소들의 Array 와 K 를 더하여 List<Integer> 로 반환하는 문제이다.
>> <https://leetcode.com/problems/add-to-array-form-of-integer/>


### 로직
서로 덧셈을 하되, 자리수만 잘 맞추어 주면 된다.

다음 숫자를 더해보자 123 + 912, 처음에는 [1, 2, 3+912]. 를 하면 3번째 값은 915 가 된다. 5 를 남기면, 910 이 남는데 다음차례로 넘기면서 10 으로 나누어 91 을 넘긴다.

두번째 요소는 [1, 2+91, 5]. 더하면 93 이 된다. 그럼 3 을 남기면, 90 이 남는데 다음차례로 넘기면서 10 으로 나누어 9 를 넘긴다. 마지막으로, [1+9, 3, 5] 을 덧셈하면 결과로 [1, 0, 3, 5] 이 나온다.

```java
class Solution {
    public List<Integer> addToArrayForm(int[] A, int K) {
        int i = A.length;
        int cur = K;
        List<Integer> list = new ArrayList();
        
        while (--i >= 0 || cur > 0) {
            if (i >= 0)
                cur += A[i];
            list.add(cur % 10);
            cur /= 10;
        }
        
        Collections.reverse(list);
        return list;
    }
}
```

### Complexity Analysis  
Time Complexity: O(max(N,logK)) where N is the length of A.  
Space Complexity: O(max(N,logK)). 

> 참 쉽죠?