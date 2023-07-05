---
title: "[Algorithm] 정렬알고리즘 - Bubble Sort(버블정렬)"
categories:
    - algorithm

tags:
    - algorithm
    - sort
    - java
    - bubble sort

toc: true
toc_sticky: true
toc_label: "summary"
toc_icon: "keyboard"
---

📌 작성자 개발 환경 Mac M1 PRO
{: .notice--primary}

## <span style="color:#80FF00"> 버블 정렬 (Bubble Sort)

버블 정렬은 가장 간단하고 이해하기 쉬운 정렬 알고리즘 중 하나입니다. 

이 알고리즘은 <span style="background-color: #f7ddbe; color:black"> 인접한 두 요소를 비교하여 순서가 잘못되어 있다면 위치를 교환하여 배열을 정렬하는 방식</span> 입니다. 

버블 정렬은 반복적으로 요소를 비교하고 교환하여 정렬을 수행합니다.

----------

### <span style="color:#FACC2E"> 동작 원리 </span>

버블 정렬의 동작 원리를 이해하기 위해 다음과 같은 단계를 따릅니다:

1. 배열의 첫 번째 요소부터 시작합니다.
2. 현재 요소와 그 다음 요소를 비교합니다.
3. 순서가 잘못되어 있다면 두 요소의 위치를 교환합니다.
4. 다음 요소로 이동하여 비교와 교환을 반복합니다.
5. 한 번의 반복이 끝나면 가장 큰 요소가 배열의 마지막으로 이동합니다.
6. 배열의 마지막 요소를 제외하고 위의 과정을 반복합니다.
7. 모든 요소가 정렬될 때까지 위의 과정을 반복합니다.

### <span style="color:#FACC2E"> 예제 코드 </span>
#### 예제 동작 원리
다음과 같이 총 7개의 숫자가 들어있는 배열에 대해 버블 정렬 로직을 적용해 보겠습니다.
```java
{64, 34, 25, 12, 22, 11, 90}
```

<br>

먼저 64와 34를 비교, 64가 더 크기 때문에 두 수의 자리를 변경합니다.
```java
{64, 34, 25, 12, 22, 11, 90}
 ^   ^
 64 > 34 => swap
{34, 64, 25, 12, 22, 11, 90}
```

<br>

이후 64와 25를 비교, 64가 더 크기 때문에 두 수의 자리를 변경합니다.
```java
{34, 64, 25, 12, 22, 11, 90}
     ^   ^
 64 > 25 => swap
{34, 25, 65, 12, 22, 11, 90}
```

<br>

비교하는 두 수가 자리 변경이 필요없을 경우는 유지합니다.
```java
{34, 25, 12, 22, 11, 64, 90}
                     ^   ^   
 64 > 90 => no swap
{34, 25, 12, 22, 11, 64, 90}
```
<br>

이 과정을 반복하다보면 맨 끝부터 큰 수로 정렬되게 됩니다.


------------------------
#### 예제 자바 코드
아래는 Java 언어로 구현된 버블 정렬의 예제 코드입니다.

```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // 두 요소의 위치를 교환합니다.
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        System.out.println("정렬 이전 배열: " + Arrays.toString(arr));

        bubbleSort(arr);

        System.out.println("정렬 이후 배열: " + Arrays.toString(arr));
    }
}
```
<br>

위의 코드에서 **bubbleSort** 메서드는 주어진 정수 배열 **arr** 을 입력으로 받아서 버블 정렬을 수행합니다.

<span style="background-color: #f7ddbe; color:black"> 두 개의 반복문을 사용하여 모든 요소를 비교하고 필요한 경우 위치를 교환</span> 합니다.

이 과정을 반복하여 배열을 정렬합니다.

----------

### <span style="color:#FACC2E"> 시간 복잡도 </span>

버블 정렬의 최악 및 평균 시간 복잡도는 O(n^2)입니다. 배열의 크기가 커질수록 성능이 저하되기 때문에, 대규모 데이터에는 적합하지 않습니다. 

최선의 경우에도 두 번째 반복문은 모든 비교를 수행하므로 O(n^2)입니다.

<img width="525" src="https://github.com/hanmingi/hanmingi.github.io/assets/22022390/7d1f7ea6-2655-4466-8fcb-b2503a0a8c13">

O(n^2)로 수행하는 다른 정렬 방법인 선택정렬을 같은 크기의 배열(약 6만개)로 정렬해볼 때 걸리는 시간이 <br>
각각 <span style="background-color: #f7ddbe; color:black"> 선택정렬은 약 11초 버블정렬은 약 23초</span>로 2배 가까이 차이나는 것을 볼 수 있습니다.

----------

### <span style="color:#FACC2E"> 장단점 </span>

버블 정렬은 다음과 같은 장단점을 가지고 있습니다:

#### <span style="color:#FACC2E"> 장점 </span>

- 구현이 간단하고 이해하기 쉽습니다.
- 추가적인 메모리 공간이 필요하지 않습니다.
- 정렬된 배열이나 거의 정렬된 배열의 경우 성능이 좋습니다.

#### <span style="color:#FACC2E"> 단점 </span>

- 성능 면에서 비효율적입니다.
- 다른 정렬 알고리즘에 비해 속도가 느립니다.
- 동일한 값의 요소들의 순서를 보존하지 않습니다.

<br>
버블 정렬은 학습 목적이나 간단한 경우에 사용될 수 있지만, <br>
위에서 선택정렬과 비교한 결과를 확인해 볼 때 
대부분의 실제 상황에서는 다른 효율적인 정렬 알고리즘을 선호합니다.

## <span style="color:#80FF00"> ❗️결론❗️ </span>

버블 정렬은 간단한 정렬 알고리즘으로, 인접한 요소를 비교하고 교환하여 배열을 정렬합니다. 

이해하기 쉽고 구현하기 간단하지만 성능 면에서는 효율적이지 않습니다. 

따라서 실제 개발 환경에서는 다른 정렬 알고리즘을 고려하는 것이 좋습니다.