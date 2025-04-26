# Sorting Algorithm Comparison

This document presents a comparison of the performance of several sorting algorithms: Insertion Sort, Heap Sort, Merge Sort, and Quick Sort (with various cutoff values). The algorithms were tested on arrays of different sizes, and their execution time and memory usage were recorded.

## Results Summary

The following table summarizes the execution times (in milliseconds) for each algorithm and array size.

| Array Size | Insertion Sort | Heap Sort | Merge Sort | Quick Sort (no cutoff) | Quick Sort (cutoff=10) | Quick Sort (cutoff=50) | Quick Sort (cutoff=200) |
|------------|----------------|-----------|------------|------------------------|-------------------------|-------------------------|--------------------------|
| 50         | 6.261          | 8.923     | 7.981      | 8.469                  | 8.589                   | 9.193                   | 8.833                    |
| 500        | 11.329         | 11.021    | 12.916     | 12.661                 | 7.783                   | 8.662                   | 10.578                   |
| 1000       | 10.291         | 9.220     | 9.280      | 8.765                  | 7.772                   | 8.994                   | 8.519                    |
| 2000       | 12.206         | 11.200    | 13.521     | 8.989                  | 7.125                   | 7.866                   | 8.080                    |
| 5000       | 16.947         | 10.222    | 11.711     | 11.532                 | 10.854                  | 8.893                   | 7.703                    |
| 10000      | 31.805         | 9.367     | 11.331     | 11.995                 | 11.978                  | 10.619                  | 11.557                   |

## Visual Representation

A line graph is provided below to visualize the performance of the sorting algorithms across different array sizes.

<div id="chart-container" style="width: 80%; height: 400px; margin: 20px auto;">
    <canvas id="sortingChart"></canvas>
</div>

## Analysis

**Time Complexity:**

* **Insertion Sort:** Has a quadratic time complexity (O(n^2)) in the worst and average cases, which is evident from the rapid increase in execution time as the array size grows. It performs well for small arrays but becomes inefficient for larger ones.
* **Heap Sort:** Has a time complexity of O(n log n) in all cases.  Its performance is consistent across different array sizes, as seen in the graph.
* **Merge Sort:** Also has a time complexity of O(n log n) and exhibits stable performance.
* **Quick Sort:**
    * **No Cutoff:** Generally has an average time complexity of O(n log n), but its worst-case complexity is O(n^2). The graph shows it performs reasonably well.
    * **Cutoff:** Using a cutoff value improves the performance of Quick Sort for larger arrays. The optimal cutoff value varies, but in these tests, a cutoff around 50-200 seems to provide good results.  This is because smaller subarrays are sorted more efficiently by Insertion Sort.

**Memory Usage:**

* Insertion sort and Heap sort generally operate in place, resulting in lower memory overhead.
* Merge sort requires additional memory for the merge operation, leading to higher memory usage.
* Quick sort's memory usage depends on the recursion depth, which is typically O(log n) for a well-balanced pivot selection (like the median-of-three used here).

**Conclusion:**

* For small arrays, Insertion Sort can be a simple and efficient choice.
* For larger arrays, Heap Sort, Merge Sort, and Quick Sort (with an appropriate cutoff) are significantly faster due to their O(n log n) time complexity.
* Quick Sort with a cutoff provides the best performance in most cases. The cutoff helps to avoid the worst-case O(n^2) time complexity by switching to insertion sort for small subarrays.
* Merge Sort provides a stable O(n log n) performance, but it requires additional memory.
* Heap Sort offers consistent O(n log n) performance and operates in place, making it a good choice when memory usage is a concern.

## Recommendations

* For small datasets or nearly sorted data, Insertion Sort may be sufficient.
* For medium to large datasets, Quick Sort with a cutoff is generally the fastest option.
* If stable sorting is required, Merge Sort is a suitable choice.
* If memory usage is a primary concern, Heap Sort is a good option.

