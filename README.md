# `Today Update`
(Notes: "&hearts;" Welcome to visit or fork or star my LeetCode Manager @
https://github.com/jackzhenguo/LeetCodeManager
## Sort
### 324 Wiggle Sort II
*  [Github:#324 Wiggle Sort II](/Sort/WiggleSortSln.cs)
*  [CSDN:#324 Wiggle Sort II](http://blog.csdn.net/daigualu/article/details/72820281)
   * This is a great question for it involves a great idea: virtual index
   ```C#
   /// <summary>
    /// WiggleSort
    /// </summary>
    public class WiggleSortSln
    {
        private static int[] _array;

        public int[] WiggleSort(int[] array)
        {
            _array = array;
            int median = findKThLargest(_array.Length / 2);
            int left = 0, i = 0, right = _array.Length - 1;

            while (i <= right)
            {
                if (_array[newIndex(i)] > median)
                {
                    //put newIndex(i) at odd index(from 1, 3, to 5, ...)
                    swap(newIndex(left++), newIndex(i));
                    i++;
                }
                else if (_array[newIndex(i)] < median)
                {
                    //put newIndex(i) at even index(max even index to little .... ) 
                    swap(newIndex(right--), newIndex(i)); //right--, so i relatively toward right 1 step
                }
                else
                {
                    i++;
                }
            }
            return _array;
        }

        private int newIndex(int index)
        {
            return (1 + 2 * index) % (_array.Length | 1);
        }

        private void swap(int i, int j)
        {
            int tmp = _array[i];
            _array[i] = _array[j];
            _array[j] = tmp;
        }

        //based on quick sort to find the Kth largest in _array
        private int findKThLargest(int k)
        {
            int left = 0;
            int right = _array.Length - 1;
            while (true)
            {
                int pivotIndex = quickSort(left, right);
                if (k == pivotIndex)
                    return _array[pivotIndex];
                else if (k < pivotIndex)
                    right = pivotIndex - 1;
                else
                    left = pivotIndex + 1;
            }
        }

        private int quickSort(int lo, int hi)
        {
            int key = _array[lo];
            while (lo < hi)
            {
                while (lo < hi && _array[hi] >= key)
                    hi--;
                //hi is less than key, hi element moves to lo index
                _array[lo] = _array[hi];
                while (lo < hi && _array[lo] < key)
                    lo++;
                //lo is bigger than key, lo element moves to hi index 
                _array[hi] = _array[lo];
            }
            _array[lo] = key;
            return lo;
        }
    }
   ```
 ## Bit Mainpulation
### 342 Power of Four
*  [Github:#342 Power of Four](/BitManipulation/PowOfFourSln.cs)
*  [CSDN:#342 Power of Four](http://blog.csdn.net/daigualu/article/details/72821233)
---


# About it
Algorithm is tool for exercising our thinking patterns, and we can strengthen the ability to convert mathematical models into code. Whether you are engaged in artificial intelligence, in-depth learning, or advanced software development, no matter what language you use, such as C#,C++,Java,python,etc., and applying the most appropriate algorithm is always the most important point when faced with a specific problem. *Every problem in practice has its own particularity, which makes it not that easier to choose the most appropriate algorithm.* How do we write the algorithm that most efficiently apply to a practical issue? **Yes, LeetCode.** You can write an algorithm until it accepted, and do not rush to do the next question, and learn the solution someone else has submitted, `so you can solve the problem from the ability of solving the problem to that fast and efficient realm`. 

I create this respository called **leetcode-csharp** because I apply C# language to solve LeetCode and `every day` will update it and also publish it in `CSDN blog`(http://blog.csdn.net/daigualu) my blog column(http://blog.csdn.net/column/details/14761.html) Also, I will put some algorithm ideas that famous scientists have created on [My Wiki for this repository](https://github.com/jackzhenguo/leetcode-csharp/wiki) such as [Flody tortoise and hare](https://github.com/jackzhenguo/leetcode-csharp/wiki/Floyd's-Tortoise-and-Hare) and [KMP](https://github.com/jackzhenguo/leetcode-csharp/wiki/KMP-getNext) and so on. 

Anyway, welcome to view, star and fork, then contribute.

## Contributing
1. Fork it!
2. Create your feature branch: git checkout -b my-leetcode-csharp
3. Commit your changes: git commit -am 'Add some questions and better solutions'
4. Push to the branch: git push origin my-leetcode-csharp
5. Submit a pull request and enjoy! :D

## Solution List
solutions using C# for leetcode according to tags of questions
Tags are following:  
* [Array](/Array)
* [Hash Table](/HashTable)
* [Linked List](/LinkedList)
* [Math](/Math)
* [Two Pointers](/TwoPointers)
* [String](/String)
* [Binary Search](/BinarySearch)
* [Dynamic Programming](/DP)
* [Stack](/Stack)
* [Tree](/Tree)

## Details
## Array
|Number| Title(Blog URL)| 
|------|-------|
35	|[Search Insert Position](http://blog.csdn.net/daigualu/article/details/66995617)
118|	[Pascal's Triangle](http://blog.csdn.net/daigualu/article/details/67006388)
119	|[Pascal's Triangle II](http://blog.csdn.net/daigualu/article/details/67069088)
414|	[Third Maximum Number](http://blog.csdn.net/daigualu/article/details/68063481)
121|	[Best Time to Buy and Sell Stock](http://blog.csdn.net/daigualu/article/details/71038726)
66|	[Plus One](http://blog.csdn.net/daigualu/article/details/71056697)
26	|[Remove Duplicates from Sorted Array](http://blog.csdn.net/daigualu/article/details/71064545)
27|	[Remove Element](http://blog.csdn.net/daigualu/article/details/71104482)
122	|[Best Time to Buy and Sell Stock II](http://blog.csdn.net/daigualu/article/details/71104584)
268	|[Missing Number](http://blog.csdn.net/daigualu/article/details/69220202)
217|	[Contains Duplicate](http://blog.csdn.net/daigualu/article/details/71123673)
532|	[K-diff Pairs in an Array](http://blog.csdn.net/daigualu/article/details/71129806)
189|	[Rotate Array](http://blog.csdn.net/daigualu/article/details/71159419)
169	|[Majority Element](http://blog.csdn.net/daigualu/article/details/69937729)
167	|[Two Sum II - Input array is sorted](http://blog.csdn.net/daigualu/article/details/69787679)
88	|[Merge Sorted Array](http://blog.csdn.net/daigualu/article/details/69367334)
53	|[Maximum Subarray](http://blog.csdn.net/daigualu/article/details/69936974)
485	|[Max Consecutive Ones](http://blog.csdn.net/daigualu/article/details/71216338)
283	|[Move Zeroes](http://blog.csdn.net/daigualu/article/details/69329038)
448	|[Find All Numbers Disappeared in an Array](http://blog.csdn.net/daigualu/article/details/71168875)
1|	[Two Sum](http://blog.csdn.net/daigualu/article/details/68957096)
219	|[Contains Duplicate II](http://blog.csdn.net/daigualu/article/details/71166985)
566| [Reshape the Matrix](http://blog.csdn.net/daigualu/article/details/71275325)	
561| [Array Partition I](http://blog.csdn.net/daigualu/article/details/71273279)	

---

## Hash Table
|Number| Title(Blog URL)|
|------|-------|
136	|[Single number](http://blog.csdn.net/daigualu/article/details/68921131)
1| [Two Sum](http://blog.csdn.net/daigualu/article/details/68957096)
447	|[Number of Boomerangs](http://blog.csdn.net/daigualu/article/details/68958818)
463	|[Island Perimeter](http://blog.csdn.net/daigualu/article/details/68959304) 
409	|[Longest Palindrome](http://blog.csdn.net/daigualu/article/details/69053267)
438	|[Find All Anagrams in a String](http://blog.csdn.net/daigualu/article/details/71339879)
389	|[Find the Difference](http://blog.csdn.net/daigualu/article/details/71450823)
350	|[Intersection of Two Arrays II](http://blog.csdn.net/daigualu/article/details/69666351)
349	|	[Intersection of Two Arrays](http://blog.csdn.net/daigualu/article/details/69666198)
500	|[Keyboard Row](http://blog.csdn.net/daigualu/article/details/71447614)
217|	[Contains Duplicate](http://blog.csdn.net/daigualu/article/details/71123673)
204	|	[Count Primes](http://blog.csdn.net/daigualu/article/details/71366483)
202	|	[Happy Number](http://blog.csdn.net/daigualu/article/details/71433906)
219	|[Contains Duplicate II](http://blog.csdn.net/daigualu/article/details/71166985)
242	|[Valid Anagram](http://blog.csdn.net/daigualu/article/details/71358552)
290	|[Word Pattern](http://blog.csdn.net/daigualu/article/details/71358552)
205	|[Isomorphic Strings](http://blog.csdn.net/daigualu/article/details/71357419)

## Linked List
|Number| Title(Blog URL)|
|------|-------|
141	|	[Linked List Cycle](http://blog.csdn.net/daigualu/article/details/69055927)
237	|		[Delete Node in a Linked List](http://blog.csdn.net/daigualu/article/details/69055991)
83	|		[Remove Duplicates from Sorted List](http://blog.csdn.net/daigualu/article/details/69093677)
160	|	[Intersection of Two Linked Lists](http://blog.csdn.net/daigualu/article/details/69526717)
203	|[Remove Linked List Elements](http://blog.csdn.net/daigualu/article/details/69389243)
206	|	[Reverse Linked List](http://blog.csdn.net/daigualu/article/details/69372119)
234	|	[Palindrome Linked List](http://blog.csdn.net/daigualu/article/details/69388513)
21	|		[Merge Two Sorted Lists](http://blog.csdn.net/daigualu/article/details/69565969)

---

## Math    
|Number| Title(Blog URL)|
|------|-------|
231	|	[Power of Two](http://blog.csdn.net/daigualu/article/details/69102931)
268|	[Missing Number](http://blog.csdn.net/daigualu/article/details/69220202)
507	|	[Perfect Number](http://blog.csdn.net/daigualu/article/details/69233798)
9|		[Palindrome Number](http://blog.csdn.net/daigualu/article/details/72717009)
453	|	[Minimum Moves to Equal Array Elements](http://blog.csdn.net/daigualu/article/details/72354061)
13	|Roman to Integer
441	|[Arranging Coins]()
415|	[Add Strings](http://blog.csdn.net/daigualu/article/details/72356377)
400	|[Nth Digit](http://blog.csdn.net/daigualu/article/details/72572244)
367	|Valid Perfect Square
66|	[Plus One](http://blog.csdn.net/daigualu/article/details/71056697)
7|	[Reverse Integer](http://blog.csdn.net/daigualu/article/details/72464418)	
204	|[Count Primes](http://blog.csdn.net/daigualu/article/details/71366483)
202	|[Happy Number](http://blog.csdn.net/daigualu/article/details/71433906)
172	|Factorial Trailing Zeroes	
171	|[Excel Sheet Column Number](http://blog.csdn.net/daigualu/article/details/72717145)	
168	|[Excel Sheet Column Title](http://blog.csdn.net/daigualu/article/details/72638706)	
258	|Add Digits	
263	|Ugly Number	
69|	[Sqrt(x)](http://blog.csdn.net/daigualu/article/details/72578272)	
67	|[Add Binary](http://blog.csdn.net/daigualu/article/details/72638937)	
246	|Strobogrammatic Number 	
326	|Power of Three	

---

## Two Pointers
|Number| Title(Blog URL)|
|------|-------|
345	|[Reverse Vowels of a String](http://blog.csdn.net/daigualu/article/details/69257693)
125	|[Valid Palindrome](http://blog.csdn.net/daigualu/article/details/69265381)
283|	[Move Zeroes](http://blog.csdn.net/daigualu/article/details/69329038)	
88	|[Merge Sorted Array](http://blog.csdn.net/daigualu/article/details/69367334)	
234|	[Palindrome Linked List](http://blog.csdn.net/daigualu/article/details/69388513)	
349	|Intersection of Two Arrays	
167	|[Two Sum II - Input array is sorted](http://blog.csdn.net/daigualu/article/details/69787679)
350|	Intersection of Two Arrays II	
344|	Reverse String	
28|	Implement strStr()	
27	|Remove Element	
26|	Remove Duplicates from Sorted Array	
141|	Linked List Cycle	
532|	K-diff Pairs in an Array

---

## String      
|Number| Title(Blog URL)|
|------|-------|
58|	[Length of Last Word](http://blog.csdn.net/daigualu/article/details/69568460)|	31.5%|	Easy
20	|[Valid Parentheses](http://blog.csdn.net/daigualu/article/details/69569622)	|32.8%	|Easy
520	|[Detect Capital](http://blog.csdn.net/daigualu/article/details/69663210)|	52.5%|	Easy
459	|[Repeated Substring Pattern](http://blog.csdn.net/daigualu/article/details/69663545)|	38.4%|	Easy
434	|[Number of Segments in a String](http://blog.csdn.net/daigualu/article/details/69664369)	|37.0%	|Easy
408	|Valid Word Abbreviation |	27.5%	|Easy
13	|Roman to Integer	|44.6%|	Easy
14	|[Longest Common Prefix](http://blog.csdn.net/daigualu/article/details/69665015)	|31.0%	|Easy
383	|[Ransom Note](http://blog.csdn.net/daigualu/article/details/69665190)	|46.5%	|Easy
521	|Longest Uncommon Subsequence I	|46.1%	|Easy
345	|Reverse Vowels of a String|	37.9%	|Easy
28	|Implement strStr()	|27.5%	|Easy
344	|Reverse String|	58.2%|	Easy
293	|Flip Game 	|54.8%	|Easy
38	|Count and Say	|33.4%	|Easy
157	|Read N Characters Given Read4 |	29.2%|	Easy
541	|Reverse String II	|44.1%	|Easy
125	|Valid Palindrome	|25.8%	|Easy
67	|Add Binary	|31.3%	|Easy	

---

## Stack
|Number| Title(Blog URL)| Pass Rate| Degree |
|------|----------------|--------|----------|
225|[Implement Stack using Queues](http://blog.csdn.net/daigualu/article/details/70183272)|	32.0%|	Easy
496|	[Next Greater Element I](http://blog.csdn.net/daigualu/article/details/70185529)	|57.5%	|Easy
155|	[Min Stack](http://blog.csdn.net/daigualu/article/details/70185814)|	27.4%|	Easy
232|	[Implement Queue using Stacks](http://blog.csdn.net/daigualu/article/details/70186010)|	35.8%|	Easy
20|	[Valid Parentheses](http://blog.csdn.net/daigualu/article/details/69569622)|	32.9%|	Easy

---

## Binary Search
|Number| Title(Blog URL)| Pass Rate| Degree |
|------|----------------|--------|----------|
367	|[Valid Perfect Square](http://blog.csdn.net/daigualu/article/details/69787644)|	37.8%|	Easy
270|	Closest Binary Search Tree Value| 	38.8%|	Easy
167	|[Two Sum II - Input array is sorted](http://blog.csdn.net/daigualu/article/details/69787679)	|47.4%|	Easy
441	|[Arranging Coins](http://blog.csdn.net/daigualu/article/details/69788500)|	36.0%|	Easy
35|	[Search Insert Position](http://blog.csdn.net/daigualu/article/details/66995617)|	39.3%|	Easy
374	|Guess Number Higher or Lower	|34.4%|	Easy
69	|Sqrt(x)	|27.4%|	Easy|
278|	[First Bad Version](http://blog.csdn.net/daigualu/article/details/69802371)	|24.8%	|Easy
475|	Heaters	|29.7%|	Easy
350	|[Intersection of Two Arrays II](http://blog.csdn.net/daigualu/article/details/69666351)	|44.1%|	Easy
349|	[Intersection of Two Arrays](http://blog.csdn.net/daigualu/article/details/69666198)|	46.5%|	Easy

---

## Dynamic Programming
|Number| Title(Blog URL)| Pass Rate| Degree |
|------|----------------|--------|----------|
53|	[Maximum Subarray](http://blog.csdn.net/daigualu/article/details/69936974)|	39.2%|	Easy|
169|	[Majority Element](http://blog.csdn.net/daigualu/article/details/69937729)|	45.6%|	Easy|
303|	[Range Sum Query - Immutable](http://blog.csdn.net/daigualu/article/details/69938986)|	27.8%|	Easy|
276	|Paint Fence |	34.1%|	Easy|
523	|[Continuous Subarray Sum](http://blog.csdn.net/daigualu/article/details/69941770)|	21.6%|	Easy|
256|	Paint House |	45.9%|	Easy|
198|	[House Robber](http://blog.csdn.net/daigualu/article/details/69946684)|	38.1%|	Easy|
121|	Best Time to Buy and Sell Stock|40.1%	|Easy|
70|	Climbing Stairs	|39.2%|	Easy|

---

## Tree
|Number| Title(Blog URL)| Pass Rate| Degree |
|------|----------------|--------|----------|
107|	[Binary Tree Level Order Traversal II](http://blog.csdn.net/daigualu/article/details/70254459)|	39.0%|	Easy
257	|[Binary Tree Paths](http://blog.csdn.net/daigualu/article/details/70340125)|	36.8%|	Easy
501	|[Find Mode in Binary Search Tree](http://blog.csdn.net/daigualu/article/details/70341143)|	38.4%|	Easy
437	|[Path Sum III](http://blog.csdn.net/daigualu/article/details/70342773)|	39.3%	|Easy
404	|[Sum of Left Leaves](http://blog.csdn.net/daigualu/article/details/70482270)|	46.5%|	Easy
112	|[Path Sum](http://blog.csdn.net/daigualu/article/details/70482285)|	33.5%	|Easy
110	|[Balanced Binary Tree](http://blog.csdn.net/daigualu/article/details/70482667)|	36.8%	|Easy
108	|[Convert Sorted Array to Binary Search Tree](http://blog.csdn.net/daigualu/article/details/70485834)|	41.3%|	Easy
543	|[Diameter of Binary Tree](http://blog.csdn.net/daigualu/article/details/70491447)|	42.3%|	Easy
226	|[Invert Binary Tree](http://blog.csdn.net/daigualu/article/details/70536685)|	50.8%|	Easy
235	|[Lowest Common Ancestor of a Binary Search Tree](http://blog.csdn.net/daigualu/article/details/70539096)|	38.5%|	Easy
104	|[Maximum Depth of Binary Tree](http://blog.csdn.net/daigualu/article/details/70541420)|	51.7%|	Easy
111|	[Minimum Depth of Binary Tree](http://blog.csdn.net/daigualu/article/details/70543969)|	32.7%	|Easy
101	|[Symmetric Tree](http://blog.csdn.net/daigualu/article/details/70544774)|	37.9%|	Easy
100|	[Same Tree](http://blog.csdn.net/daigualu/article/details/70254478)|	45.8%|	Easy
