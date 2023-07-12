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
