# 문제 설명
---
'이진 탐색(Binary Search)' 알고리즘을 사용해서 어떤 원소가 리스트 안에 포함되어 있는지 확인하려고 한다! 이진 탐색 알고리즘은 선형 탐색 알고리즘과 달리, 정렬된 리스트를 전제로 한다. 정렬된 리스트가 아니면 이 알고리즘은 적용이 불가능하다.

그렇다면 왜 이 알고리즘의 이름이 '이진 탐색'일까?
그 이유는 한 번 비교를 거칠 때마다 탐색 범위가 대략 절반으로 줄어들기 때문이다.

예를 들어 [1, 2, 3, 5, 8, 13, 21, 34, 55] 에서 3을 찾는 경우, 알고리즘의 진행 방식은 다음과 같다!

## 시도 1
리스트의 첫 번째 인덱스와 마지막 인덱스의 값을 합하여 2로 나눈 후, 중간 인덱스로 지정한다. 그리고 그 인덱스에 해당하는 값이 3인지 확인해 본다.

이 경우 리스트의 첫 번째 인덱스는 0이고 마지막 인덱스는 8이기 때문에, 중간 인덱스는 4이고 해당 원소는 8이다.
찾고자 하는 원소 3은 중간 원소 8에 비해 작다. 리스트는 정렬되어 있으니, 이제 인덱스 4~8은 탐색 범위에서 제외시킬 수 있다. 탐색 범위가 절반으로 줄어든 것이다!

## 시도 2
탐색 범위는 이제 인덱스 0~3이다. 탐색 범위의 첫 번째 인덱스는 0이고 마지막 인덱스는 3이기 때문에, 중간 인덱스는 (0 + 3) // 2인 1이다. 인덱스 1에 해당하는 원소는 2이다.

찾고자 하는 원소 3은 중간 원소 2에 비해 크다. 리스트는 정렬되어 있으니, 이제 인덱스 0~1은 탐색 범위에서 제외시키면 된다. 탐색 범위가 다시 절반으로 줄어든 것이다!

시도 3
탐색 범위는 이제 인덱스 2~3이다. 탐색 범위의 리스트의 첫 번째 인덱스는 2이고 마지막 인덱스는 3이므로, 중간 인덱스는 (2 + 3) // 2인 2이다. 인덱스 2에 해당하는 원소의 값은 3이다.

찾고자 하는 원소 3은 중간에 해당하는 원소 3과 일치한다. 값을 찾았으니, 인덱스 2를 리턴해 주며, 알고리즘을 종료한다.


```
def binary_search(element, some_list):
    # 여기에 코드를 작성하세요

print(binary_search(2, [2, 3, 5, 7, 11]))
print(binary_search(0, [2, 3, 5, 7, 11]))
print(binary_search(5, [2, 3, 5, 7, 11]))
print(binary_search(3, [2, 3, 5, 7, 11]))
print(binary_search(11, [2, 3, 5, 7, 11]))
```
```
0
None
2
1
4
```