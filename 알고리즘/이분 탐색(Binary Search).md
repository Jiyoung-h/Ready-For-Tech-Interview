# 이분 탐색(Binary Search)

- 탐색 범위를 두 부분으로 분할하면서 찾는 방식
- 처음부터 끝까지 돌면서 탐색하는 것보다 훨씬 빠름
- 시간복잡도
    - 전체 탐색 : ```O(N)```
    - 이분 탐색 : ```O(logN)```
- 정렬이 되어 있는 상태에서, left와 right, mid 값 설정
- mid와 찾는 값을 비교
    - mid < M : left = mid + 1
    - mid > M : right = mid - 1
- left > right 가 될 때 까지 반복
```
int solution(int[] arr, int M) { 
    Arrays.sort(arr);
	int start = 0;
	int end = arr[arr.length-1];
	while(start <= end) {
		int sum = 0;
		int mid = (start+end)/2;
		for (int i = 0; i < arr.length; i++) {
			if(arr[i] > mid)
				sum+=mid;
			else
				sum+=arr[i];
		}
		if(sum > M)
			end = mid - 1;
		else
			start = mid + 1;
	}
	return end;
}
```
