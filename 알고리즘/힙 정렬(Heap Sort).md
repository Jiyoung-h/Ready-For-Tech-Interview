# 힙 정렬(Heap Sort)

- 완전 이진 트리를 기본으로 하는 힙(Heap) 자료구조 기반 정렬 방식
- ```완전 이진 트리``` : 삽입할 때 왼쪽부터 차례대로 추가하는 이진 트리
- 최대 힙 (Max-heap)을 구성
- 현재 힙 루트는 가장 큰 값이 존재하므로 루트의 값을 마지막 요소와 바꾼 후, 힙 사이즈를 하나 줄임
- 다시 최대 힙을 구성
- 힙의 사이즈가 1이 될 때까지 반복


```
void heapSort(int[] array) {
    int n = array.length();
    
    // max heap 초기화
    // 부모 노드의 인덱스를 기준으로 왼쪽/오른쪽 자식노드 (2i+1)/(2i+2)
    for (int i = n/2-1; i>=0; i--){
        heapify(array, n, i); 
    }
    
    // extract 연산
    for (int i = n-1; i>0; i--) {
        swap(array, 0, i);  // 교환
        heapify(array, i, 0); // 다시 최대 힙 구성
    }
}
void heapify(int array[], int n, int i) {
    int p = i;
    int l = i*2 + 1;
    int r = i*2 + 2;
    
    //왼쪽 자식노드
    if (l < n && array[p] < array[l]) {
        p = l;
    }
    //오른쪽 자식노드
    if (r < n && array[p] < array[r]) {
        p = r;
    }
    //부모노드 < 자식노드
    if(i != p) {
        swap(array, p, i);
        heapify(array, n, p);
    }
}
```

- 퀵정렬과 합병정렬의 성능이 좋기 때문에 힙 정렬의 사용빈도는 높지 않음
- 시간복잡도 : ```O(nlogn)```

### 힙 정렬이 유용할 때
- 가장 크거나 가장 작은 값을 구할 때
- 최대 k만큼 떨어진 요소들을 정렬할 때

### 단점
- 불안정 정렬
- 시간적 비효율
