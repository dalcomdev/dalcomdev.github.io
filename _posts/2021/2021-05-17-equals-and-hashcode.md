---
published: true
toc: true
categories:
  - java
---

## equals and hashCode contract
- 2개의 object 에 대해, equals() 가 true 이면, hashCode() 도 서로 같아야 합니다. 
- 2개의 object 에 대해, equals() 가 false 이면, hashCode() 가 같을 수도 다를수도 있다.

간단히 말하면 a.equals(b) 이면 a.hashCode() == b.hashCode() 입니다. 

위 contract 을 만족시키기 위해 equals() 를 override 했으면 반드시 hashCode() 도 override 해서 구현해야 합니다.

그렇지 않으면 contract violation 입니다.

## equals() 를 override 했으면 hashCode() 도 override 해야 한다?
뭐 살짝 contract 안지킬수도 있지 빌드도 잘되고 아무 이상없는데?
라고 할 수도 있지만, hash 기반 collection 을 사용할 경우는 다시 생각해 봐야 합니다. 내부 구현에서 equals() 와 hashCode() 가 사용되기 때문이죠.

아래는 Effective Java 의 내용 일부인데, equals() 를 override 했으면, hashCode() 도 override 해야 하는 이유를 설명합니다.

> You must override hashCode in every class that overrides equals. If you fail to do so, your class will violate the general contract for hashCode, which will prevent it from functioning properly in collections such as HashMap and HashSet.

## HashMap 에서의 bucket 과 hashCode(), equals() 의 관계
아래 이미지는 HashMap 의 데이터 저장구조 입니다.

![image](https://user-images.githubusercontent.com/9858389/118408507-dba60a00-b6c0-11eb-977e-4f6331cfe3c5.png)

HashMap, HashSet 같은 hash 기반 collection 에서는 데이터 저장시,

- hashCode() 를 키값으로 bucket 에 저장하고 같은 값이 있을경우(hash collision), 내부적으로 LinkedList 에 넣습니다.

위에서 보듯이 hashCode() 를 제대로 구현하지 않으면 hash collision 자주 일어나게되고, 데이터 추가/삭제시 퍼포먼스가 느려지겠죠.  왜냐하면 한번에 키값으로 bucket 에서 값을 가져오지 못하고 bucket → LinkedList 를 거쳐서 가져와야 하니까요.

## 정리
equals() 를 override 하게되면, hashCode() 도 override 해주어야 한다.  그렇지 않으면 hashCode 의 contract 을 어기게 되고, 이는 HashMap, HashSet 같은 hash 기반 collection 에서 정상적으로 동작하지 않을 수 있다.