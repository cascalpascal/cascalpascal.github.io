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
Selection Sort is an algorithm similar to Bubble Sort. In this algorithm, the location to insert elements in each cycle is already determined, and it selects which elements to insert.

You may be confused about Selection Sort and Insertion Sort, but it is convenient to think of Selection Sort as selecting a position in an array and finding the value at that position.

It is good to know as this is an algorithm that often appears in technical interviews or exams (*sorted state on the nth cycle*).

<br>

## Process
1. The algorithm iterates through the unsorted subarray to find the smallest element.
2. Once the smallest element is found, it is swapped with the first element of the unsorted subarray, effectively adding it to the end of the sorted subarray.
3. The algorithm then moves the boundary of the sorted subarray one position to the right, considering the element just added to be part of the sorted subarray.
4. Steps 1-3 are repeated until the entire array is sorted.

![[selection-sort-001.gif]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/selection-sort-001.gif?raw=true)

<br>

## Time Complexity: O(n^2)
If there are n elements in the array, the number of comparisons in the first cycle is n-1(1 through (n-1)). In the second cycle, n-2(2 through n-1).

(n-1) + (n-2) + (n-3) + .... + 2 + 1 => n(n-1)/2  

Sorting a given array of n elements takes **O(n^2)** time, assuming that the comparison is done in constant time. The time complexity for the best, average, and worst cases is the same as O(n^2).

<br>

## Space Complexity: O(n)
Selection Sort is an in-place sorting algorithm, meaning it sorts the elements within the input array itself without requiring additional memory space except for a few variables for temporary storage and loop indices.
Therefore, the space complexity of Selection Sort is **O(n)**, which indicates that it uses constant space regardless of the input size.

<br>

## Pros
- Simple and easy to understand.
- *In-place sorting*. It doesn't require additional memory space.
- The number of comparison is large, however, compared to Bubble Sort, the actual number of swaps is relatively low, making it relatively efficient for datasets requiring numerous exchanges.

<br>

## Cons
- *Inefficient*. Time complexity is O(n^2).
- *Unstable Sort.*


<br>

## Code

```python
# selection_sort.py

def selection_sort(arr):
    n = len(arr)

    # 배열을 하나씩 순회하면서 정렬되지 않은 부분 배열에서 최소값을 찾아서 정렬된 부분 배열로 이동시킴
    for i in range(n - 1):
        # 정렬되지 않은 부분 배열에서 최소값의 인덱스를 찾음
        min_index = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        # 최소값과 현재 위치를 교환
        arr[i], arr[min_index] = arr[min_index], arr[i]

# 테스트를 위한 리스트
test_list = [58, 66, 50, 28, 8, 27, 91]

# Selection Sort를 이용하여 리스트를 정렬
selection_sort(test_list)

print("Sorted list:")
print(test_list)

```


```java
// SelectionSort.java

public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int indexMin, temp;
        // 위치(index)를 선택해줌
        for (int i = 0; i < arr.length-1; i++) {
            indexMin = i;
            // i+1번째 원소부터 선택한 위치의 값과 비교를 시작함
            for (int j = i + 1; j < arr.length; j++) {
                // 현재 선택한 자리에 있는 값보다 순회하고 있는 값이 작다면, 위치를 갱신함.
                if (arr[j] < arr[indexMin]) {
                    indexMin = j;
                }
            }
            // swap(arr[indexMin], arr[i])
            // indexMin과 처음 선택한 위치에 들어가야 하는 값의 위치를 서로 swap 함.
            temp = arr[indexMin];
            arr[indexMin] = arr[i];
            arr[i] = temp;
      }
    }
    
    // Selection Sort 결과 출력
    public static void printArray(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; ++i) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    //텍스트를 위한 메인 메소드
    public static void main(String[] args) {
        int[] testArray = {58, 66, 50, 28, 8, 27, 91};
        System.out.println("Test array:");
        printArray(testArray);

        // Selection Sort를 이용하여 배열 정렬
        selectionSort(testArray);

        System.out.println("Sorted array:");
        printArray(testArray);
    }
}

```





<br>



---
## Reference
- https://gyoogle.dev/blog/algorithm/Selection%20Sort.html
- https://github.com/GimunLee/tech-refrigerator/blob/master/Algorithm/resources/selection-sort-001.gif
- ChatGPT, "Tell me about Bubble Sort"