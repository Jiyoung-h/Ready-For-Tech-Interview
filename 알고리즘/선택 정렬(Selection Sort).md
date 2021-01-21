# 선택 정렬(Selection Sort)
- 해당 자리에 넣을 원소를 찾는 알고리즘
- 1st : 최소값을 찾아 맨 앞의 원소와 교환 
- 2nd : 맨 앞의 원소를 제외하고 최소값을 찾아 두번째 원소와 교환
- n-th : 앞 (n-1)개의 원소를 제외하고 최소값을 찾아 n번째 원소와 교환
```
void selectionSort(int[] arr) {
    int indexMin, temp;
    for (int i = 0; i < arr.length()-1; i++) {       // 자리 선택
        indexMin = i;
        for (int j = i + 1; j < arr.length(); j++) { 
            if (arr[j] < arr[indexMin]) {    // 최소값을 찾는 과정
                indexMin = j;
            }
        }
        temp = arr[indexMin];       // 최소값과 해당 자리 원소와 교환
        arr[indexMin] = arr[i];
        arr[i] = temp;
  }
  System.out.println(Arrays.toString(arr));
}
```
- 시간복잡도 : ```O(n^2)```
- 공간복잡도 : ```O(n)```

### 장점
- 단순하다
- 비교 횟수는 많지만 실제 교환하는 횟수는 적다
- 공간적 효율 : 제자리 정렬

### 단점
- 시간적 비효율적
- 불안정 정렬 : 동일한 값에 대해 기존의 순서가 유지되지 않는 정렬 방식
(안정 정렬 : 동일한 값에 대해 기존의 순서가 유지되는 정렬 방식)
