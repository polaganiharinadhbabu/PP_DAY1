# DAY 1 — PYTHON FUNDAMENTALS & PROBLEM SOLVING

**Name:** POLAGANI HARINADH BABU  
**Date:** 26/10/2026  
**Day:** 1

## 1. Coding Problem — First Non-Repeating Character

### Approach

I used a dictionary to count the frequency of each character. First, I removed spaces from the input string. Then, I counted each character using a dictionary. Finally, I traversed the string again and returned the first character whose frequency was 1.

This approach preserves the original order and keeps uppercase and lowercase characters distinct.

### Code

```python
def first_non_repeating(text):
    text = text.replace(" ", "")
    freq = {}

    for char in text:
        freq[char] = freq.get(char, 0) + 1

    for char in text:
        if freq[char] == 1:
            return char

    return "No non-repeating character found"


print(first_non_repeating("programming"))
print(first_non_repeating("aabbcdd"))
print(first_non_repeating("aabbcc"))
```

### Test Inputs and Outputs

```python
print(first_non_repeating("programming"))
# p

print(first_non_repeating("aabbcdd"))
# c

print(first_non_repeating("aabbcc"))
# No non-repeating character found

print(first_non_repeating("a"))
# a

print(first_non_repeating("   "))
# No non-repeating character found

print(first_non_repeating("AabA"))
# a
```

### Time and Space Complexity

- **Time Complexity:** O(n), because the string is traversed twice.
- **Space Complexity:** O(k), where k is the number of distinct non-space characters stored in the dictionary.

## 2. Concept Question — List, Tuple, Set and Dictionary

| Feature | List | Tuple | Set | Dictionary |
|---|---|---|---|---|
| Order | Ordered | Ordered | No positional order guarantee | Insertion order preserved |
| Duplicates | Allowed | Allowed | Unique elements only | Keys must be unique |
| Mutable | Yes | No, shallowly immutable | Yes | Yes |
| Main use | Ordered records that change | Fixed groups of values | Uniqueness and membership | Key-value lookup |

### Scenario 1 — Unique Student IDs

I would use a **set** to store student IDs because a set keeps only unique elements. It is also useful for checking whether an ID has already been processed.

### Scenario 2 — Student Profile Fields

I would use a **dictionary** to store a student's name, email and phone number because each field can be mapped to its corresponding value.

Example:

```python
student = {
    "name": "Ravi",
    "email": "r@example.com"
}

student["phone"] = "9999999999"

print(student.get("grade", "Not assigned"))
```

## 3. Debugging Challenge — Student Search

### Issue

The original code prints `"Student not found"` for every student who does not match `"Kiran"`. The `else` belongs to the `if` inside the loop, so it executes for each nonmatching student even if Kiran appears later.

### Fixed Code

```python
students = ["Ravi", "Anil", "Kiran", "Suresh"]

for student in students:
    if student == "Kiran":
        print("Student found:", student)
        break
else:
    print("Student not found")
```

### Explanation

The `break` stops the loop when Kiran is found. The `for/else` block executes the `else` only if the loop finishes without a `break`. Therefore, the program prints one correct result.

## 4. What I Learned

I learned Python fundamentals, data types, mutable and immutable objects, loops, conditions, functions, and common data structures. I also learned how to use a dictionary for character frequency counting and how to use a set for uniqueness. The coding problem helped me understand how to solve a problem using a clear approach and test different edge cases.

## 5. What I Found Difficult

I found it challenging to understand how dictionary frequency counting works and how to identify the first non-repeating character while preserving the original order. Debugging the student-search loop was also challenging because the `else` was placed inside the loop. Practising the code with different inputs helped me understand these concepts better.

## 6. Improvement After Mentor Feedback

After receiving mentor feedback, I would review my approach, test empty strings and repeated characters, and check whether the output is correct for uppercase and lowercase characters. I would also improve my explanation of time and space complexity and practise writing the solution without looking at the reference code.
