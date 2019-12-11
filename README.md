# Problemas de codificação em Nim-lang

Perguntas diárias sobre problemas de codificação resolvidas usando nimlang

1. [Dado um matriz de números, retorne a soma do primeiro e ultimo elemento.](https://github.com/Nim-br/coding-problems-in-nim/blob/master/day1.nim)
```
# Dado um matriz de números, retorne a soma do primeiro e ultimo elemento.
# Por exemplo, tempos [10, 15, 3, 7] and K of 17, resposta 10 + 7 é 17.

let testArray = [10,15, 3,7]
let K = 17

proc anyTwoSumstoK [I,](arr: array[I,int], K: int): bool =

    for loc_1,i in arr.pairs:
        for loc_2,j in arr.pairs:
            if (i + j == K) and (loc_1 != loc_2): return true
    
    return false

echo anyTwoSumstoK(testArray,K)
```
2. Given an array of integers, return a new array such that each element at index i of the new array is the product of all the numbers in the original array except the one at i. Solve it without using division and in O(n) time.

```
import math

var arr1 = [1,2,3,4,5]
var arr2 =  [3,2,1]

proc exclusiveProduct [S,](arr: array[S,int]): array[S,int] =

    for loc,i in arr: result[loc] = 1
    var
        prodLeft = 1
        prodRight = 1
        len = arr.high
        leftMult: int
        rightMult: int

    for i in 0..arr.high:
        leftMult = arr[i]
        rightMult = arr[len - i]
        result[i] *= prodLeft
        result[len - i] *= prodRight
        prodLeft *= leftMult
        prodRight *= rightMult

echo repr exclusiveProduct(arr1)
echo repr exclusiveProduct(arr2)
```
3. Given the root to a binary tree, implement serialize(root), which serializes the tree into a string, and deserialize(s), which deserializes the string back into the tree.
4. Given an array of integers, find the first missing positive integer in linear time and constant space. In other words, find the lowest positive integer that does not exist in the array. The array can contain duplicates and negative numbers as well.For example, the input [3, 4, -1, 1] should give 2. The input [1, 2, 0] should give 3. You can modify the input array in-place.
5. cons(a, b) constructs a pair, and car(pair) and cdr(pair) returns the first and last element of that pair. 
6. An XOR linked list is a more memory efficient doubly linked list. Instead of each node holding next and prev fields, it holds a field named both, which is a XOR of the next node and the previous node. Implement a XOR linked list; it has an add(element) which adds the element to the end, and a get(index) which returns the node at index.
7. Given the mapping a = 1, b = 2, ... z = 26, and an encoded message, count the number of ways it can be decoded.
8. A unival tree (which stands for "universal value") is a tree where all nodes have the same value. Given the root to a binary tree, count the number of unival subtrees.
9. Given a list of integers, write a function that returns the largest sum of non-adjacent numbers. Numbers can be 0 or negative.
10. Implement a job scheduler which takes in a function f and an integer n, and calls f after n milliseconds.
11. Implement an autocomplete system. That is, given a query string s and a set of all possible query strings, return all strings in the set that have s as a prefix. For example, given the query string de and the set of strings [dog, deer, deal], return [deer, deal]. Hint: Try preprocessing the dictionary into a more efficient data structure to speed up queries.
12. There exists a staircase with N steps, and you can climb up either 1 or 2 steps at a time. Given N, write a function that returns the number of unique ways you can climb the staircase. The order of the steps matters.
13. Given an integer k and a string s, find the length of the longest substring that contains at most k distinct characters.
14. The area of a circle is defined as πr^2. Estimate π to 3 decimal places using a Monte Carlo method.
15. Given a stream of elements too large to store in memory, pick a random element from the stream with uniform probability.
16. You run an e-commerce website and want to record the last N order ids in a log. Implement a data structure to accomplish this, with the following API: - record(order_id): adds the order_id to the log, - get_last(i): gets the ith last element from the log. i is guaranteed to be smaller than or equal to N. You should be as efficient with time and space as possible.
17. Given a string representing the file system in the above format, return the length of the longest absolute path to a file in the abstracted file system. If there is no file in the system, return 0.
18. Given an array of integers and a number k, where 1 <= k <= length of the array, compute the maximum values of each subarray of length k.
19. A builder is looking to build a row of N houses that can be of K different colors. He has a goal of minimizing cost while ensuring that no two neighboring houses are of the same color. Given an N by K matrix where the nth row and kth column represents the cost to build the nth house with kth color, return the minimum cost which achieves this goal.
20. Given two singly linked lists that intersect at some point, find the intersecting node. The lists are non-cyclical.
21. Given an array of time intervals (start, end) for classroom lectures (possibly overlapping), find the minimum number of rooms required.
22. Given a dictionary of words and a string made up of those words (no spaces), return the original sentence in a list. If there is more than one possible reconstruction, return any of them. If there is no possible reconstruction, then return null.
23. You are given an M by N matrix consisting of booleans that represents a board. Each True boolean represents a wall. Each False boolean represents a tile you can walk on. Given this matrix, a start coordinate, and an end coordinate, return the minimum number of steps required to reach the end coordinate from the start. If there is no possible path, then return null. You can move up, left, down, and right. You cannot move through walls. You cannot wrap around the edges of the board.
24. Implement locking in a binary tree. A binary tree node can be locked or unlocked only if all of its descendants or ancestors are not locked.
25. Implement regular expression matching with the following special characters: - . (period) which matches any single character, - * (asterisk) which matches zero or more of the preceding element
26. Given a singly linked list and an integer k, remove the kth last element from the list. k is guaranteed to be smaller than the length of the list.
27. Given a string of round, curly, and square open and closing brackets, return whether the brackets are balanced (well-formed).
28. Write an algorithm to justify text. Given a sequence of words and an integer line length k, return a list of strings which represents each line, fully justified.
29. Run-length encoding is a fast and simple method of encoding strings. The basic idea is to represent repeated successive characters as a single count and character. For example, the string "AAAABBBCCDAA" would be encoded as "4A3B2C1D2A". Implement run-length encoding and decoding. You can assume the string to be encoded have no digits and consists solely of alphabetic characters. You can assume the string to be decoded is valid.
30. You are given an array of non-negative integers that represents a two-dimensional elevation map where each element is unit-width wall and the integer is the height. Suppose it will rain and all spots between two walls get filled up. Compute how many units of water remain trapped on the map in O(N) time and O(1) space.
31. The edit distance between two strings refers to the minimum number of character insertions, deletions, and substitutions required to change one string to the other. For example, the edit distance between “kitten” and “sitting” is three: substitute the “k” for “s”, substitute the “e” for “i”, and append a “g”. Given two strings, compute the edit distance between them.
32.Suppose you are given a table of currency exchange rates, represented as a 2D array. Determine whether there is a possible arbitrage: that is, whether there is some sequence of trades you can make, starting with some amount A of any currency, so that you can end up with some amount greater than A of that currency. There are no transaction costs and you can trade fractional quantities.
