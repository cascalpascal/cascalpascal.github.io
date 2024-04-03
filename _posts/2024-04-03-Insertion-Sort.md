---
layout: post
author: Cascal Pascal
tags:
  - algorithm
  - tech-interview
---

>**Course**
>
>[[Major] Algorithm](https://cascalpascal.github.io/major-tech-interview)

>**Bookmarks**
>
>- [Process](#process)
>
>- [Time Complexity](#time-complexity:-o(n),-o(n^2))
>
>- [Space Complexity](#space-complexity:-o(n))
>
>- [Pros and Cons](#pros)
>
>- [Code](#code)


---

Insertion Sort is one of the *simplest* yet *efficient* sorting algorithms. It is an algorithm that starts from the second element, specifies the position to insert by comparing it to the elements in front (left), then moves the element to the back and inserts the data in the designated position to sort it.

It has an incredibly fast efficiency of **O(n)** in the best case, making it a good sorting algorithm that can be used as part of other sorting algorithms.

<br>

## Process
1. The algorithm starts by traversing from the second element, save the value of the second element (index) in temp.
2. It is inserted by comparing temp with previous elements.
3. Repeat this process until all elements are inserted into the sorted part.

<br>

## Time Complexity: O(n), O(n^2)
In the case where everything is sorted (Optimal), the comparison is performed only once, so the time complexity is **O(n)**. 
In the average and worst case (if sorted in reverse) **O(n^2)**, $(n-1) + (n-2) + (n-3) + .... + 2 + 1 => n(n-1)/2$ .

Additionally, when inserting/removing data one by one from an already sorted array, it is realistically the best sorting algorithm because the overhead excluding search is very low.

<br>

## Space Complexity: O(n)
It sorts the elements within the input array itself without requiring additional memory space, except for a few variables for temporary storage and loop indices.

Therefore, the space complexity of Insertion Sort is **O(n)**, which indicates that it uses constant space regardless of the input size.

<br>

## Pros
- Simple and easy to understand.
- *In-place sorting*. It doesn't require additional memory space.
- *Efficient* for nearly sorted lists or small-sized lists.
- *Stable Sort.*

<br>

## Cons
- In the average and worst case, the time complexity is O(n^2), which is *inefficient*.
- It becomes more inefficient as the length of the array increases.

<br>

## Code

```python
# insertion_sort.py

def insertion_sort(arr):
    # 배열의 길이를 저장
    n = len(arr)

    # 배열의 각 요소를 정렬된 부분에 삽입
    for i in range(1, n):
        key = arr[i]  # 현재 삽입할 값을 임시로 저장
        j = i - 1

        # key보다 큰 값을 찾아서 오른쪽으로 이동시킴
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        
        # key를 적절한 위치에 삽입
        arr[j + 1] = key

# 테스트를 위한 리스트
test_list = [58, 66, 50, 28, 8, 27, 91]

# Insertion Sort를 이용하여 리스트를 정렬
insertion_sort(test_list)

print("정렬된 리스트:")
print(test_list)
```

```java
// InsertionSort.java

public class InsertionSort {
    public static void insertionSort(int[] arr) {

        // 첫 번째 원소 앞에는 어떤 원소도 존재하지 않기 때문에, 두 번째 index부터 탐색함함
        // temp에 임시로 해당 index 값을 저장하고, prev에는 해당 index의 이전 위치를 저장함
        for(int index = 1 ; index < arr.length ; index++){
            int temp = arr[index];
            int prev = index - 1;

            // 이전 index를 가리키는 prev가 음수가 아니고, 이전 index의 값이 위에서 선택한 값보다 크다면,
            // 서로 값을 교환하고 prev를 더 이전 index를 가리키도록 함
            while( (prev >= 0) && (arr[prev] > temp) ) {
               arr[prev+1] = arr[prev];
               prev--;
            }

            // prev에는 현재 temp 값보다 작은 값들 중 제일 큰 값의 위치를 가리킴
            // 따라서, prev+1에 temp값을 넣어줌
            arr[prev + 1] = temp;
         }
    }

    // Insertion Sort 결과 출력
    public static void printArray(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; ++i) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    //텍스트를 위한 메인 메소드
    public static void main(String[] args) {
        int[] arr = {58, 66, 50, 28, 8, 27, 91};
        System.out.println("Test array:");
        printArray(arr);

        // Insertion Sort를 이용하여 배열 정렬
        insertionSort(arr);

        System.out.println("Sorted array:");
        printArray(arr);
    }
}
```


<br>

---

## Reference

- https://github.com/GimunLee/tech-refrigerator/blob/master/Algorithm/%EC%82%BD%EC%9E%85%20%EC%A0%95%EB%A0%AC%20(Insertion%20Sort).md#%EC%82%BD%EC%9E%85-%EC%A0%95%EB%A0%AC-insertion-sort
- ChatGPT, "Tell me about Insertion Sort"