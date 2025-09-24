📒 Notes: HashMaps & Sets in JavaScript
1. HashMap (Objects & Map in JS)
🔹 What is a HashMap?

A key-value data structure where keys are mapped to values using a hashing function.

In JS, you can use:

Objects {} → keys are strings/symbols.

Map → keys can be any type (number, object, array, etc).

🔹 Basic Operations (using Map)
let map = new Map();

// Insert
map.set("name", "Yasir");
map.set("age", 23);

// Access
console.log(map.get("name")); // Yasir

// Check existence
console.log(map.has("age")); // true

// Delete
map.delete("age");

// Size
console.log(map.size); // 1

// Iteration
for (let [key, value] of map) {
  console.log(key, value);
}

🔹 Real-World Example: Word Frequency Counter
function wordFrequency(str) {
  let words = str.split(" ");
  let freqMap = new Map();

  for (let word of words) {
    freqMap.set(word, (freqMap.get(word) || 0) + 1);
  }

  return freqMap;
}

console.log(wordFrequency("i love js and i love coding"));
// Map { 'i' => 2, 'love' => 2, 'js' => 1, 'and' => 1, 'coding' => 1 }

🔹 Time Complexity

Insertion → O(1)

Deletion → O(1)

Lookup/Search → O(1)

Iteration → O(n)

2. Set
🔹 What is a Set?

A collection of unique values (no duplicates).

Preserves insertion order.

🔹 Basic Operations
let set = new Set();

// Insert
set.add(1);
set.add(2);
set.add(2); // ignored, since duplicate

// Check existence
console.log(set.has(1)); // true

// Delete
set.delete(1);

// Size
console.log(set.size); // 1

// Iteration
for (let val of set) {
  console.log(val);
}

🔹 Real-World Example: Remove Duplicates from an Array
let arr = [1, 2, 2, 3, 4, 4, 5];
let uniqueArr = [...new Set(arr)];

console.log(uniqueArr); // [1, 2, 3, 4, 5]

🔹 Time Complexity

Insertion → O(1)

Deletion → O(1)

Search → O(1)

Iteration → O(n)

3. HashMap vs Set
Feature	HashMap (Map)	Set
Stores	Key-Value pairs	Unique values only
Duplicate Keys	❌ Not allowed	❌ Not allowed
Duplicate Values	✅ Allowed	❌ Not allowed
Order	Preserves insertion order	Preserves insertion order
Example Usage	Word count, caching, lookups	Unique items, membership test