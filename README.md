# Python Full Stack Placement Preparation — Day 1

**Name:** P. Harinadh Babu  
**Date:** 26/10/2026  
**Day:** 1

## Task A: First Non-Repeating Character

 1. Approach

- First, create an empty dictionary to store the frequency of each character.
- Ignore spaces while counting characters.
- Use a dictionary to count how many times each character appears.
- Traverse the string again and return the first character whose frequency is 1.
- If no such character exists, return a suitable message.
- Uppercase and lowercase characters are treated as different characters.

 2. Python Code

def first_non_repeating(text):
    a = {}

  for i in text:
        if i != " ":
            if i in a:
                a[i] = a[i] + 1
            else:
                a[i] = 1

  for i in text:
        if i != " " and a[i] == 1:
            return i

  return "No non-repeating character found"

 3. Test Cases

print(first_non_repeating("programming"))
# Expected output: p

print(first_non_repeating("aabbcdd"))
# Expected output: c

print(first_non_repeating("aabbcc"))
# Expected output: No non-repeating character found

print(first_non_repeating("Aabb"))
# Expected output: A

print(first_non_repeating("   "))
# Expected output: No non-repeating character found

 4. Time and Space Complexity

- **Time Complexity:** O(n), because the string is traversed twice.
- **Auxiliary Space Complexity:** O(k), where k is the number of distinct non-space characters stored in the dictionary.

## Task B: Python Data Structures

1. Difference Between List, Tuple, Set, and Dictionary

| Data Structure | Ordered | Duplicates | Mutable |
|---|---|---|---|
| List | Yes | Yes | Yes |
| Tuple | Yes | Yes | No |
| Set | No positional order guarantee | No | Yes |
| Dictionary | Yes (insertion order) | Keys: No; values: Yes | Yes |

 2. Scenario: Storing Unique Student IDs

I would use a **set** because it stores unique values and automatically prevents duplicate student IDs.

student_ids = {101, 102, 103, 101}
print(student_ids)

Expected output (order may vary):
{101, 102, 103}

Adding an ID that already exists does not create a duplicate. Set membership checks are O(1) on average.

 3. Scenario: Storing Student Profile Details

I would use a **dictionary** because it stores information as key-value pairs.

student = {
    "id": 101,
    "name": "Kiran",
    "age": 21,
    "course": "Python Full Stack"
}

print(student["name"])
print(student.get("course"))

Expected output:
Kiran
Python Full Stack

Using 'get()' can help avoid a 'KeyError' when a key is missing. Required fields should also be validated.

## Task C: Debugging

### Problem

The goal is to print exactly one message: either that Kiran was found or that the student was not found.

### Corrected Code

students = ["Ravi", "Anil", "Kiran", "Suresh"]

for student in students:
    if student == "Kiran":
        print("Student found:", student)
        break
else:
    print("Student not found")

### Explanation

The `break` statement stops the loop when Kiran is found. The `else` block belongs to the `for` loop, so it executes only when the loop finishes without encountering `break`.

This ensures that only one correct message is printed.

## Task D: Reflection
1. What approach did I use?

I used a dictionary to count character frequencies and then traversed the string again to find the first character that appears only once.

2. What did I learn today?

I learned how to use dictionaries for frequency counting, how Python data structures differ, and how `break` and `for...else` work in loops.

3. What was difficult?

Understanding how to ignore spaces, handle strings with no non-repeating characters, and place the `else` block correctly was challenging.

 4. What would I improve after mentor feedback?

I would improve variable naming, test more edge cases, and write reusable functions instead of keeping all the logic in a direct input-based script.

