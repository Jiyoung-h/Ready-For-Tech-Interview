### 거품 정렬(Bubble Sort)
- 서로 인접한 두 원소의 대소를 비교하고, 조건에 맞지 않으면 자리를 교환하며 정렬하는 알고리즘
- 1round : arr[i]와 arr[i+1]를 비교하여 교환 => 가장 큰 원소가 마지막으로 이동
- 2round : 같은 방법으로 마지막 원소를 제외하고 반복
- n-round : 뒤에서 (n-1)개의 원소를 제외하고 반복
```
void bubbleSort(int[] arr) {
    int temp = 0;
	for(int i = 0; i < arr.length(); i++) {       
		for(int j= 1 ; j < arr.length-i(); j++) {
			if(arr[j-1] > arr[j]) {            
				temp = arr[j-1];
				arr[j-1] = arr[j];
				arr[j] = temp;
			}
		}
	}
}
```
- 시간복잡도 = ```O(n^2)```
- 공간복잡도 = ```O(n)```
### 장점
- 구현이 간단하고, 직관적
- 다른 메모리 공간을 필요로 하지 않음 (제자리 정렬)
### 단점
- 시간복잡도가 비효율적
- 교환 연산이 매우 빈번하게 일어남
