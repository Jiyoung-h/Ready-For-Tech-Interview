# 퀵 정렬(Quick Sort)

- 분할 정복 (divide and conquer) : 문제를 작은 2개의 문제로 분리하고 각각을 해결한 다음, 결과를 모아서 원래의 문제를 해결하는 전략
- 배열 중 하나의 원소를 골라 ```피벗(pivot)``` 이라고 한다.
- 분할 : ```피벗```앞에는 ```피벗```보다 작은 값의 원소들, 뒤에는 ```피벗```보다 큰 값의 원소들이 오도록 ```피벗```을 기준으로 배열을 둘로 나눈다.
- 분할된 두 개의 배열에 대해 재귀적으로 과정을 반복
- 재귀 호출이 반복될 때마다 최소한 하나의 원소는 위치가 정해지므로, 반드시 끝난다는 보장이 있음

```
void quickSort(int i, int j)    // i부터 j까지 정복
{
	if(i>=j) return;            
	int pivot = quick[(i+j)/2]; // 가운데 값을 피벗
	int left = i;
	int right = j;
	
	while(left<=right)     
	{
		while(quick[left]<pivot) left++;    
		while(quick[right]>pivot) right--;  
		// left, right 값이 피벗보다 크거나 작아질 때까지 이동
		
		if(left<=right)
		{
			swap(quick[left],quick[right]);
			left++; right--;
		}
	}
	// 분할
	quickSort(i,right);
	quickSort(left,j);
}
```
### 퀵 정렬 개선
- 피벗 값이 최소나 최대값으로 지정되어 파티션이 나눠지지 않을 때 ```O(n^2)``` 시간복잡도
- 가운데 값을 피벗으로 뒀을 때 ```O(nlog₂n)``` 시간복잡도

- 시간복잡도
    - 최선(Best cases) : ```T(n) = O(nlog₂n)```
        - 비교 횟수 ```log₂n```
        - 비교 연산 ```n```
    - 최악(Worst cases) : ```T(n) = O(n^2)```
        - 비교 횟수 ```n```
        - 비교 연산 ```n```
    - 평균(Average cases) : ```T(n) = O(nlog₂n)```

- 공간복잡도 : ```O(n)```

### 장점
- 시간적 효율성
- 공간적 효율성

### 단점
- 불안정 정렬
- 오히려 정렬된 배열일 때 불균형 분할에 의해 수행시간이 오래 걸린다.
