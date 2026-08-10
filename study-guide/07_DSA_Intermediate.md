# 📁 FOLDER 07 — DSA INTERMEDIATE ⭐ HIGH PRIORITY

## Covers: Two Pointers · Sliding Window · Hashing · Strings · Linked List · Stack/Queue Advanced

---

## ❓ QUESTIONS + SOLUTIONS

---

## SECTION A: Two Pointers ⭐

### What is the Two-Pointer Technique?

- Use **two indices** (left/right or slow/fast) to solve problems in O(n) instead of O(n²)
- Works on **sorted arrays** or when you can reason about pointer movement

---

### Q1. Two Sum in Sorted Array
```java
int left = 0, right = arr.length - 1;
while (left < right) {
  int sum = arr[left] + arr[right];
  if (sum == target) return new int[]{left, right};
  else if (sum < target) left++;
  else right--;
}
```

---

### Q2. Reverse a String / Check Palindrome ⭐
```java
// Check palindrome
String s = "racecar";
int left = 0, right = s.length() - 1;
boolean isPalin = true;
while (left < right) {
  if (s.charAt(left) != s.charAt(right)) { isPalin = false; break; }
  left++; right--;
}
```

---

### Q3. Remove Duplicates from Sorted Array (Two Pointers)
```java
int i = 0;
for (int j = 1; j < arr.length; j++) {
  if (arr[j] != arr[i]) arr[++i] = arr[j];
}
return i + 1; // new length
```

---

### Q4. 3Sum ⭐
```java
// Sort first, then fix one element and use two pointers for remaining
Arrays.sort(nums);
for (int i = 0; i < nums.length - 2; i++) {
  if (i > 0 && nums[i] == nums[i-1]) continue; // skip duplicates
  int left = i + 1, right = nums.length - 1;
  while (left < right) {
    int sum = nums[i] + nums[left] + nums[right];
    if (sum == 0) { result.add(Arrays.asList(nums[i], nums[left], nums[right])); left++; right--; }
    else if (sum < 0) left++;
    else right--;
  }
}
```

---

### Q5. Container with Most Water ⭐
```java
int left = 0, right = heights.length - 1, maxArea = 0;
while (left < right) {
  int area = Math.min(heights[left], heights[right]) * (right - left);
  maxArea = Math.max(maxArea, area);
  if (heights[left] < heights[right]) left++;
  else right--;
}
```

**🧠 Remember:** Move the shorter wall inward — you can only gain area if the shorter wall increases.

---

## SECTION B: Sliding Window ⭐

### What is Sliding Window?

- A **window** (subarray/substring) that slides over the array
- Avoid recomputing the whole window each step — add new element, remove old element
- Use for: max sum, longest substring, fixed-size windows

---

### Q6. Maximum Sum Subarray of Size K ⭐
```java
int windowSum = 0, maxSum = 0;
// Build initial window
for (int i = 0; i < k; i++) windowSum += arr[i];
maxSum = windowSum;

// Slide the window
for (int i = k; i < arr.length; i++) {
  windowSum += arr[i] - arr[i - k]; // add new, remove old
  maxSum = Math.max(maxSum, windowSum);
}
```

---

### Q7. Longest Substring Without Repeating Characters ⭐ 🔥
```java
Map<Character, Integer> map = new HashMap<>();
int left = 0, maxLen = 0;
for (int right = 0; right < s.length(); right++) {
  char c = s.charAt(right);
  if (map.containsKey(c) && map.get(c) >= left) {
    left = map.get(c) + 1; // shrink window
  }
  map.put(c, right);
  maxLen = Math.max(maxLen, right - left + 1);
}
```

**🧠 Remember:** Sliding window + HashMap = "expand right, shrink left when duplicate found"

---

## SECTION C: Hashing ⭐

### Q8. Count Frequencies of Array Elements
```java
Map<Integer, Integer> freq = new HashMap<>();
for (int x : arr) freq.put(x, freq.getOrDefault(x, 0) + 1);
```

---

### Q9. First Non-Repeating Element ⭐
```java
// Step 1: Count frequencies
Map<Integer, Integer> freq = new HashMap<>();
for (int x : arr) freq.put(x, freq.getOrDefault(x, 0) + 1);
// Step 2: Find first with count == 1
for (int x : arr) if (freq.get(x) == 1) return x;
```

---

### Q10. Find Duplicates Using Hashing
```java
Set<Integer> seen = new HashSet<>();
for (int x : arr) {
  if (!seen.add(x)) System.out.println("Duplicate: " + x);
}
```

---

### Q11. Longest Consecutive Sequence in O(n) ⭐
```java
Set<Integer> set = new HashSet<>();
for (int x : arr) set.add(x);
int maxLen = 0;
for (int x : set) {
  if (!set.contains(x - 1)) { // only start from sequence beginning
    int len = 1;
    while (set.contains(x + len)) len++;
    maxLen = Math.max(maxLen, len);
  }
}
```

---

### Q12. Group Anagrams ⭐
```java
Map<String, List<String>> map = new HashMap<>();
for (String word : words) {
  char[] chars = word.toCharArray();
  Arrays.sort(chars);
  String key = new String(chars);  // "eat", "tea", "ate" all → "aet"
  map.computeIfAbsent(key, k -> new ArrayList<>()).add(word);
}
```

---

## SECTION D: Strings ⭐

### Q13. Check Anagrams ⭐
```java
// Sort both strings and compare
char[] a = s1.toCharArray(); Arrays.sort(a);
char[] b = s2.toCharArray(); Arrays.sort(b);
return Arrays.equals(a, b);

// OR: count character frequencies
int[] count = new int[26];
for (char c : s1.toCharArray()) count[c - 'a']++;
for (char c : s2.toCharArray()) count[c - 'a']--;
for (int x : count) if (x != 0) return false;
return true;
```

---

### Q14. String Immutability in Java ⭐

**Definition:** Once a String object is created, its content **cannot be changed**.

```java
String s = "hello";
s = s + " world";  // Does NOT modify "hello" — creates a NEW String object
```

**Why immutable?**
- Thread safety (can be shared between threads safely)
- String Pool (JVM can cache and reuse literals)
- Security (Strings used in DB connections, network — must not change)

**StringBuilder for repeated modification:**
```java
// Bad (creates many temp Strings)
String result = "";
for (int i = 0; i < 1000; i++) result += i;

// Good — O(n) not O(n²)
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 1000; i++) sb.append(i);
String result = sb.toString();
```

---

### Q15. Check if String is Rotation of Another ⭐
```java
// "abcde" is rotation of "cdeab"?
// Trick: if s2 is a rotation of s1, then s2 appears in s1+s1
String doubled = s1 + s1;
return doubled.contains(s2) && s1.length() == s2.length();
```

---

## SECTION E: Linked List ⭐

### Q16. Reverse a Linked List ⭐ 🔥
```java
ListNode prev = null, curr = head;
while (curr != null) {
  ListNode next = curr.next;
  curr.next = prev;  // reverse pointer
  prev = curr;
  curr = next;
}
return prev; // new head
```

**🧠 Remember:** 3 pointers: `prev`, `curr`, `next`. Reverse one link at a time.

---

### Q17. Find Middle Node (Floyd's Slow/Fast) ⭐
```java
ListNode slow = head, fast = head;
while (fast != null && fast.next != null) {
  slow = slow.next;
  fast = fast.next.next;
}
return slow; // slow is at middle
```

---

### Q18. Detect Cycle (Floyd's Cycle Detection) ⭐
```java
ListNode slow = head, fast = head;
while (fast != null && fast.next != null) {
  slow = slow.next;
  fast = fast.next.next;
  if (slow == fast) return true; // cycle detected!
}
return false;
```

**🧠 Remember:** Floyd's = "tortoise and hare" — fast catches slow if there's a cycle.

---

### Q19. Merge Two Sorted Linked Lists ⭐
```java
ListNode dummy = new ListNode(0), curr = dummy;
while (l1 != null && l2 != null) {
  if (l1.val <= l2.val) { curr.next = l1; l1 = l1.next; }
  else { curr.next = l2; l2 = l2.next; }
  curr = curr.next;
}
curr.next = (l1 != null) ? l1 : l2;
return dummy.next;
```

---

## SECTION F: Stack/Queue Advanced ⭐

### Q20. Check Balanced Parentheses ⭐ 🔥
```java
Stack<Character> stack = new Stack<>();
for (char c : s.toCharArray()) {
  if (c == '(' || c == '[' || c == '{') stack.push(c);
  else {
    if (stack.isEmpty()) return false;
    char top = stack.pop();
    if ((c == ')' && top != '(') || (c == ']' && top != '[') || (c == '}' && top != '{'))
      return false;
  }
}
return stack.isEmpty();
```

---

### Q21. Next Greater Element (Monotonic Stack) ⭐
```java
int[] result = new int[arr.length];
Arrays.fill(result, -1);
Stack<Integer> stack = new Stack<>(); // stores indices

for (int i = 0; i < arr.length; i++) {
  while (!stack.isEmpty() && arr[i] > arr[stack.peek()]) {
    result[stack.pop()] = arr[i]; // arr[i] is NGE for top of stack
  }
  stack.push(i);
}
```

**What is a Monotonic Stack?** A stack that maintains elements in monotonically increasing or decreasing order. Used for NGE, largest rectangle, trapping rainwater.

---

### Q22. Implement Queue Using Stacks
```java
Stack<Integer> s1 = new Stack<>(), s2 = new Stack<>();
// Enqueue: push to s1
// Dequeue: if s2 empty, transfer all from s1 to s2, then pop s2
```

---

## 🔑 QUICK MEMORY TRICKS

- **Two pointers:** Left + Right converging, or Slow + Fast
- **Sliding window:** Fixed window = add right, remove left
- **HashMap pattern:** Store what you've seen, check complement
- **Floyd's cycle:** Slow + Fast pointers → meet if cycle
- **Balanced parentheses:** Stack — open=push, close=check+pop
- **Reverse linked list:** 3 pointers: prev, curr, next

---

## ⚠️ COMMON MISTAKES

1. Forgetting to sort before using two pointers on unsorted data
2. Off-by-one in sliding window (window size = right - left + 1)
3. Not handling empty stack before pop() in parentheses check
4. Losing track of next pointer before reversing linked list link
5. Forgetting cycle detection needs `fast.next != null` check
