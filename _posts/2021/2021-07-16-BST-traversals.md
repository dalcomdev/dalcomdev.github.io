---
published: true
toc: true
categories:
  - algorithm
tags:
  - algorithm
---

## BST traversals - InOrder, PreOrder and PostOrder
> BST 에서 tree node 를 순회하는 3가지 방법에 대해 알아본다.

![image](https://user-images.githubusercontent.com/9858389/125830331-efadb165-e10a-4376-a4ce-636dda312d91.png)  

위 그림 기준으로 아래와 같이 정의할 수 있다. 항상 느끼는거지만, 이론을 알고나면 간단하다...
아래에서 트리를 어떤 순수로 방문할 것인가 확실히 이해하면 게임끝 이라고 볼 수 있다.  

Depth First Traversals: 
(a) Inorder (Left, Root, Right) : 4 2 5 1 3 
(b) Preorder (Root, Left, Right) : 1 2 4 5 3 
(c) Postorder (Left, Right, Root) : 4 5 2 3 1

### InOrder
노드를 Left, Root, Right 순으로 방문한다.
```java
public static List<Integer> inOrderTraverse(BST tree, List<Integer> array) {
  if (tree == null) return array;
  
  inOrderTraverse(tree.left, array);
  array.add(tree.value);
  inOrderTraverse(tree.right, array);
  
  return array;
}
```

### PreOrder
노드를 Root, Left, Right 순으로 방문한다.
```java
public static List<Integer> preOrderTraverse(BST tree, List<Integer> array) {
  if (tree == null) return array;
  
  array.add(tree.value);
  preOrderTraverse(tree.left, array);
  preOrderTraverse(tree.right, array);
  
  return array;
}
```

### PostOrder
노드를 Left, Right, Root 순으로 방문한다.
```java
public static List<Integer> postOrderTraverse(BST tree, List<Integer> array) {
  if (tree == null) return array;
  
  postOrderTraverse(tree.left, array);
  postOrderTraverse(tree.right, array);
  array.add(tree.value);
  
  return array;
}
```

### 결론
재귀호출을 생각해보면 노드를 각자 in, pre, post 순서대로 방문하는것을 알 수 있다.  
원리를 알면 너무나 쉽지만, 모를때는 풀기 쉽지 않은 문제이다...

* 참고: https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/