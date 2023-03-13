# 버블 정렬(Bubble sort)

- 버블 정렬은 정렬하지 않은 배열의 첫 번째 요소와 인접한 요소를 비교하여 제일 뒤에 가장 큰 값을 배치하도록 정렬하는 알고리즘이다.
- 정렬 방법은 다음과 같다.
  - 첫 번째 원소와 두 번째 원소를 비교하여 더 큰 값을 뒤쪽으로 교체한다.
  - 두 번째 원소와 세 번째 원소를 비교허여 더 큰 값을 뒤쪽으로 교체한다.
  - $...$
  - 배열의 위치를 하나씩 증가하여 배열의 끝까지 반복하면 가장 큰 값이 제일 뒤에 정렬된다.
  - 정렬된 값을 제외하고 동일한 작업을 반복한다.

버블 정렬의 장점은 구현이 쉽고, 데이터가 제자리에서 정렬되어 메모리 오버헤드가 거의 없다.
단점은 모든 요소를 계속해서 비교하기 때문에 비교 횟수가 많고, 교환이 필요한 경우 매번 바꿔줘야 하기 때문에 교환 횟수도 많아 비효율적이다.

버블 정렬의 평균 시간 복잡도는 $O(n^2)$이다. 정렬되어 있는지 여부와 관계없이 배열의 끝까지 비교해야 하기 때문에 최선, 최악, 평균 시간 복잡도가 모두 동일하다.

버블 정렬은 배열의 모든 인덱스에 접근해야 하기 때문에 기본적으로 $O(n)$의 시간 복잡도를 가지며, 한 번의 순회가 끝나면 비교 대상이 하나씩 줄어들어 $n-1$번 순회하면 정렬이 끝난다.

각 회차 정렬에 따라 시간 복잡도를 구하면

$(n-1) + (n-2) + ... + 2 + 1$

$= n(n-1)/2$

$= O(n^2)$ 이므로 버블 정렬의 평균 시간 복잡도는 $O(n^2)$이다.