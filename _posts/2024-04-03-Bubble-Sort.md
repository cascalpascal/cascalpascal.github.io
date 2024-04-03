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
>- [Time Complexity](#time-complexity:-on^2)
>
>- [Space Complexity](#space-complexity:-on)
>
>- [Pros and Cons](#pros)
>
>- [Code](#code)


---
Bubble Sort  is an algorithm similar to Selection Sort. This algorithm traverses the list, comparing adjacent pairs of elements and swapping their positions if necessary to eventually sort the list. It is one of the *simplest* but *inefficient* sorting algorithms.

<br>

## Process
1. Traverse the list and compare adjacent pairs of elements. If the current element is greater than the next element, swap their positions. Repeat this comparison and swapping process until reaching the end of the list.
2. After one iteration, the largest (or the smallest) element is moved to the end. Therefore, in the second iteration, the last element is excluded from the sorting process, and after the second iteration, the last two elements are excluded from the sorting process. This way, with each iteration of the sorting process, one more element is excluded from consideration.

<br>

## Time Complexity: O(n^2)
(n-1) + (n-2) + (n-3) + .... + 2 + 1 => n(n-1)/2  
Since Bubble Sort compares two elements, whether sorted or not, the time complexity is the same in the best, average, and worst cases as **O(n^2)**.

<br>

## Space Complexity: O(n)
Bubble Sort is an in-place sorting algorithm, meaning it sorts the elements within the input array itself without requiring additional memory space. Therefore, the space complexity of Bubble Sort is **O(n)**, which indicates that it uses constant space regardless of the input size.

<br>

## Pros
- Simple and easy to understand.
- *In-place sorting*. It doesn't require additional memory space.
- *Stable Sort*.

<br>

## Cons
- *Inefficient*. Time complexity is O(n^2).
- To reach their sorted positions from unsorted ones, there are numerous swap operations involved.
- It performs poorly especially for large datasets or nearly sorted lists.

<br>

## Code

```python
# BubbleSort.py

def BubbleSort(arr):
    n = len(arr)
    
    # 리스트를 순회하면서 비교-교환 과정을 반복
    for i in range(n):
        # 각 순회마다 리스트 끝까지 비교-교환을 진행하며 가장 큰 원소를 찾음
        for j in range(0, n-i-1):
            # 현재 원소가 다음 원소보다 크다면 위치를 교환
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

# 테스트를 위한 리스트
test_list = [58, 66, 50, 28, 8, 27, 91]

# Bubble Sort를 이용하여 리스트를 정렬
BubbleSort(test_list)

print("Sorted list: ")
print(test_list)
```

```java
// BubbleSort.java

public class BubbleSort {
    // Bubble Sort 알고리즘 구현
    public static void bubbleSort(int[] arr) {
        int temp = 0;
        
        // 제외될 원소의 갯수를 의미. 
        // 1회전이 끝나면 배열의 끝에는 가장 큰 원소가 있으므로 하나씩 증가시킴.
        for(int i = 0; i < arr.length; i++) {
	        // 원소를 비교할 index를 뽑을 반복문. 
	        // j는 현재 원소를 가리키고, j-1은 이전 원소를 가리키므로, j는 1부터 시작함.
            for(int j= 1 ; j < arr.length-i; j++) {
            
	            // 현재 가르키고 있는 두 원소의 대소를 비교.
                if(arr[j-1] > arr[j]) {
                
                    // swap(arr[j-1], arr[j])
                    temp = arr[j-1];
                    arr[j-1] = arr[j];
                    arr[j] = temp;
                }
            }
        }
    }


    // Bubble Sort 결과 출력
    public static void printArray(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; ++i) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    // 테스트를 위한 메인 메소드
    public static void main(String[] args) {
        int[] testArray = {58, 66, 50, 28, 8, 27, 91};
        System.out.println("Test Array:");
        printArray(testArray);

        // Bubble Sort를 이용하여 배열 정렬
        bubbleSort(testArray);

        System.out.println("Sorted Array:");
        printArray(testArray);
    }
}
```



<br>




---

## Reference

- https://gyoogle.dev/blog/algorithm/Bubble%20Sort.html
- ChatGPT, "Tell me about Bubble Sort"