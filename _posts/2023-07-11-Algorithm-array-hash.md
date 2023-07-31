---
layout: post
title: Algorithm-Array & Hash
date: 2022-08-16
excerpt: "Array & Hash"
tags: [Algorithm, code, Python]
comments: False
---

## Array & summary

{% highlight java %}
Set<Integer> set = new HashSet<Integer>();
{% endhighlight %}


## Scenes 
- Contains Duplicate: HashSet
- 
---

## Leetcode
### [217. Contains Duplicate](https://github.com/liangliang1120/leetcode/blob/main/solutions/Hashing_217.py)
- hashset = set(); hashset.add(n)
- Set<Integer> set = new HashSet<Integer>(); set.contains(x); set.add(x);
- Time: O(N) (HashSet, sort is O(nlogn))
- Space:O(N)

### [242. Valid Anagram](https://github.com/liangliang1120/leetcode/blob/main/solutions/0242-Valid-Anagram.py)
- len(s) != len(t)? shash = defaultdict(int); for sn in s: shash[sn] += 1, return thash == shash
- s.length() != t.length()? Map<Character, Integer> shash = new HashMap<>();for (char c : s.toCharArray()) {shash.put(c, shash.getOrDefault(c, 0) + 1);} return thash.equals(shash);

### [1. Two Sum](https://github.com/liangliang1120/leetcode/blob/main/solutions/0001-Two-Sum.py)
- Map<Integer, Integer> hash = new HashMap<>();
- hash.containsKey(target - value_i)
- return new int[] { i, hash.get(target - value_i) };
- hash.put(value_i, i);

## [49 Group Anagrams](https://github.com/liangliang1120/leetcode/blob/main/solutions/0049-Group-Anagrams.py)
- 26 characters: key is the [0]*26, each digit represent the a-z [!!!tuple the list as the dict key]
- time: O(mn26),M is the number of words,n is the average length of a word,
- space: O(mk), M is the number of words,k is the longest length of the words in str

## [347 Top K Frequent Elements](https://github.com/liangliang1120/leetcode/blob/main/solutions/0347-Top-K-Frequent-Elements.py)
- count hashmap, frequency hashmap, from top frequency to 0 for loop to add res untill the end
- Time: O(n), Space: O(n)

## [238. Product of Array Except Self](https://github.com/liangliang1120/leetcode/blob/main/solutions/0238-Product-of-Array-Except-Self.py)
- compute the prefix and postfix and then get the outcome
- Time: O(n), Space: O(n)

## [36. Valid Sudoku](https://github.com/liangliang1120/leetcode/blob/main/solutions/0036-Valid-Sudoku.py)
- Each row must contain the digits 1-9 without repetition.
- Each column must contain the digits 1-9 without repetition.
- Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.
- define 3 rules as defaultdict(set)
- Time: O(n), Space: O(n)   





