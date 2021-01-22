# 병합 정렬(Merge Sort)

- 분할 정복 방법 (Divide and Conquer)
- 요소를 쪼갠 후, 다시 합병시키면서 정렬 => 쪼개는 방법은 퀵 정렬과 유사
- 순차적인 비교로 정렬하므로 LinkedList의 정렬이 필요할 때 사용하면 효율적 
   (퀵 정렬은 임의 접근으로 성능이 좋지 않음)
```
    void mergeSort(int[] a, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;
            mergeSort(a, left, mid); // 왼쪽 부분 배열을 나눈다.
            mergeSort(a, mid + 1, right); // 오른쪽 부분 배열을 나눈다.
            merge(a, left, mid, right);
            // 나눈 부분 배열을 합친다.
        }
    }
    
    void merge(int[] a, int left, int mid, int right) {
        int i, j, k, l;
        i = left;
        j = (mid + 1);
        k = left;
        // 작은 원소 순서대로 sorted 배열에 채워 넣음
        while (i <= mid && j <= right) {    
            if (a[i] < a[j]) sorted[k++] = a[i++];
            else sorted[k++] = a[j++];
        }

        // 왼쪽 부분 배열이 sorted 에 모두 채워지면
        // 남아 있는 오른쪽 부분 배열의 값을 일괄 복사
        if (mid < i) {
            for (l = j; l <= right; l++) sorted[k++] = a[l];
        } else {
            // 오른쪽 부분 배열이 sorted 배열에 정렬된 상태로 모두 채워지면
            // 남아 있는 왼쪽 부분 배열의 값을 일괄 복사
            for (l = i; l <= mid; l++) sorted[k++] = a[l];
        }
        // 원본 배열인 a 배열로 다시 복사
        for (l = left; l <= right; l++) a[l] = sorted[l];
    }
```
- 시간복잡도
    - 평균 : ```O(nlogn)```
    - 최선 : ```O(nlogn)```
    - 최악 : ```O(nlogn)```

### 장점
- 데이터의 분포에 상관없이 정렬되는 시간은 동일
- 안정 정렬

### 단점
- 임시 배열이 필요하다 (제자리 정렬이 아니다)
- 레코드의 크기가 큰 경우 이동 횟수가 많으므로 시간적 낭비
