# DSA Learning Guide

Welcome to a guide designed for an efficient and intuitive exploration of Data Structures and Algorithms (DSA). If you're in search of direct resources and links, this may not be the right place. Our goal is to inspire self-directed research, independent learning, and hands-on exercise implementation. Delve into the topics, conduct personal research, and tackle exercises to foster a comprehensive, self-driven learning experience. This isn't a quick journey; mastering these topics takes time—months, not days. If you're ready for a deep dive and hands-on application, you're in the right space.

Sequentially explore each topic and implement the exercises in your preferred language (C++/Rust/Zig/Nim recommended; Go/Java acceptable). Avoid dynamically typed, garbage-collected languages without pointer support. Steer clear of JS and Python. This structured approach ensures a focused and efficient learning experience tailored to languages emphasizing control and explicit memory management.

## 1. Understanding memory
Understanding memory is the core of working with data structures and algorithms, Strong memory layout knowledge and manipulation skills are required. Explore the topics one by one and delve into the exercise whenever you feel comfortable.
1. Computer memory  and How memory works
2. Stack vs Heap?
3. Dynamic memory allocation and management.
4. Pointers or Smart pointers (Reference counting, Unique pointer etc.).

#### Exercise:
Implement `vector<T>` data structure in your language and should be compliant with these key features:
1. Sequential, homogeneous data structure with constant time random access to its elements.
2. Growable and Shrinkable in terms of memory and capacity.
3. Should be generic over the type T (type of the element in sequence).
4. Should contain these operations at least
	1. **append/push_back**: Inserts a value to the last of the sequence.
	2. **prepend/push_front**: Insets a value in front (starting) of the sequence.
	3. **pop_back**: Remove the last element from the sequence and return its value to the caller.
	4. **remove_last**: Removes the last element and immediately frees memory.
	5. **pop_front**: Removes the first element from the sequence and returns its value to the caller.
	6. **remove_front**: Removes the first element and immediately frees memory.
	7. **len/size**: Number of elements in the sequence.
	8. **capacity**: the number of elements that can be added before reallocating memory.
	9. **remove_at**: Removes an element at any given index if it exists
	10. **delete**: Delete a particular element from the array if it matches.
	11. **clear**: Delete all elements and release the memory
	12. \[OPTIONAL] **sort**: sort the given sequence *in-place* as efficiently as possible.
5. Can be constructed with preoccupied and *initialized to default* memory.
6. Use the best error/exception handling possible provided by the language that you're using.

Things to take care
1. An operation that fails should be either a compile time error or a runtime exception that can be handled by the caller.
2. No memory should be leaked or kept more than required.
3. The user of your vector should be able to make a mental model of correct underlying memory (means operations are atomic, stable, intuitive and consistent)
4. All operations should abstract away the underlying data or pointer from the user, they can only use underlying data using the methods specified above, anything else should remain private.


*Note: Expect a 2-3 week completion timeframe for this exercise, or potentially a week if full-time dedication is possible. Beyond completion, focus on learning memory allocation, exception handling, memory safety, and language design patterns. The goal is not just finishing but gaining insights from the process.*

## 2. Linked List
Linked List is not used so much in production code now, but the concept is important to understand. Things you will learn from LL are
1. Proper memory management.
2. Handling chaotic data on the heap.
3. Set the basis of a more complex data structure like graphs and trees.
4. Understanding runtime complexity and tradeoffs.
5. Linked List vs Array (in terms of memory and runtime complexity).
6. What are the specific use cases for Linked List where it outshines generic arrays?

These learnings form a solid understanding of essential principles applicable beyond Linked Lists in software development.
The exercise will act as learning material for this topic, research, understand and code your idea.

### Exercise
Build a `LinkedList<T>`  data structure in your language and should be compliant with these key features:
1. Sequential, homogeneous data structure with linear time access to its elements but constant time insertion/deletion at any place.
2. Should be generic over the type T (type of the element in sequence).
3. Should contain these operations
	1. **append/push_back**: Inserts a value to the last of the sequence.
	2. **prepend/push_front**: Insets a value in front (starting) of the sequence.
	3. **pop_back**: Removes the last element from the sequence and returns its value to the caller.
	4. **remove_last**: Removes the last element and immediately frees memory.
	5. **pop_front**: Removes the first element from the sequence and returns its value to the caller.
	6. **remove_front**: Removes the first element and immediately frees memory.
	7. **len/size**: Number of elements in the sequence.
	8. **Remove**: remove a particular element from the whole linked list.
	9. **sort**: sort the given linked list *in-place* as efficiently as possible.
	10. **clear**: Delete all nodes and clean memory.
4. Use the best error/exception handling possible by the language you're using.

Things to take care
1. An operation that fails should be either a compile time error or a runtime exception that can be handled by the caller.
2. No memory should be leaked or kept more than required.
3. The user of your linked list should be able to make a mental model of correct underlying memory (means operations are atomic, stable, intuitive and consistent)
4. All operations should abstract away the underlying data, Node, or pointer from the user, they can only use the method specified above, anything else should remain private.

## 3. Complexity Analysis
Understanding runtime and space complexity is crucial for programmers. When faced with multiple algorithms that accomplish the same task differently, you must compare them based on how fast they run (runtime) and how much memory they use (space complexity). As a programmer, your responsibility is to choose the algorithm that best suits your use case, ensuring it performs efficiently and doesn't consume unnecessary resources. This knowledge helps optimize software, making it more responsive and resource-friendly.

Things to learn
1. Run time complexity analysis (Big O, Big *theta*, Big *omega*)
2. Space complexity analysis
3. Amortized analysis (Why do we need it)
4. Space-time tradeoff

### Exercise
To understand complexity better, we should do an analysis ourselves, hence both the programs that you wrote earlier, `vector<T>` and `linkedlist<T>`, run each operation for 1 million data points and analyze the runtime and/or space complexity.

You can follow these steps as described to make things easier
1. append 1.5 million elements in Vector and Linked List and check their runtime.
2. from the same data container made earlier, randomly remove 1 million x indexed elements and compare the runtime.
3. from the same data container, delete all elements in the most efficient way possible (preferably implement a `clean()` operation on both) and compare the run time.
4. insert 1 million elements at random index in both the container and compare their runtime.
5. search for a random element in both containers 1000 times and compare runtime.
6. sort both containers with the most efficient algorithm you have written and compare the runtime.
7. Document and try to mathematically prove your observation

These would've given you enough hints about which Data Structure to use in which situation based on the runtime/space tradeoff

Think about which operation will be super-fast when done on a HashSet rather than these two sequential data structures. What drawbacks come with HashSet?

## 4. Graph
At a certain juncture in your journey with computers, you'll start seeing everything as a graph. Graphs, being remarkably versatile data structures, find applications across various domains. Their flexibility allows them to be employed in numerous scenarios, making them a fundamental and powerful tool in the world of computing.

Things to learn with graph
1. What are graphs? (mathematically).
2. How can we represent that mathematical model in computer memory?
3. How can we run graph-based algorithms like BFS, and DFS on the memory representation that you chose?
4. Finding MST, SSSP, MSSP
5. Learn generally used graph algorithms
	1. Breadth-First Search (BFS)
	2. Depth-First Search (DFS)
	3. Dijkstra's Algorithm
	4. Bellman-Ford Algorithm
	5. Floyd-Warshall Algorithm
	6. Kruskal's Algorithm
	7. Prim's Algorithm
	8. Topological Sorting
	9. Tarjan's Algorithm
	10. A* Search Algorithm

### Exercise
Represent the metro map of your (or nearby) city using graph data structure with these requirements fulfilled
1. We can check the shortest path from station A to B
2. We can calculate the price from A to B (Following the Metro pricing scheme)
3. Prioritize less used routes if the user is relaxed on time, otherwise fastest route possible (eg: some metro lines are crowded as compared to others)
4. Use different path-finding algorithms and choose the best from them based on what a person would think about the shortest routes.

Things to take care
1. An operation that fails should be either a compile time error or a runtime exception that can be handled by the caller.
2. No memory should be leaked or kept more than required.
3. The user of your program should be able to perform actions without deep knowledge of the underlying principle.
4. All operations should be fast enough for users patience to check metro routes. I would assume 500ms is the maximum time you can spend on one operation.
5. All data in the program should be accurate and parsed from a file in a parseable format like *YAML*, *JSON*, *TOML*, *XML*, *KDL* etc.

*Note: Invest at least a month to properly understand, implement and refine the code you've written by exploring the graph algorithms through optimizing the public transportation. The purpose of this immersive exercise isn't only to make you familiar with the topic but to help you delve deeper by providing practical insights into real-world problem solving, system optimization and a comprehensive mastery of the graph algorithms. Remember, patience and perseverance is the key to mastering the skills that this article can't offer.*

[1] https://new.mta.info/maps


---
*Take a break*
These 4 topics would have taken you enough time and you are now capable of modelling/structuring data in memory and running algorithms on them. It's a long way even if it doesn't seem like it. Take a moment and appreciate yourself, look back at all the code you have written, clean it if you think it can be, make it presentable and write it in your achievements. Let's move forward with more.

---

## 5. Tree
You must be questioning, why Graph before Trees? The reason is that trees are just graphs without cycles due to this speciality, there is a set of algorithms that only works on trees and not graphs, but all Graph algorithms work on trees.

This section will take the longest time to learn and understand all types of trees why they are needed, and where they are used.

You have to learn about these to understand Tree and most importantly, their implementation and use cases
1. Tree
2. Binary Tree
3. Binary Search Tree
4. AVL Tree
5. Why AVL tree if there is BST?
6. Red-Black Tree
7. B Tree
8. B+ Tree
9. Segment Tree
10. Trie

### Exercise
Making a single exercise involving most of the concepts was difficult, but I tried my best to include most of the spectrum. 

Design and Implement a virtual filesystem which includes these specifications
1. Every file/folder in the system is a node
2. Every node has its metadata that contains these at a minimum
	1. **created_at**: Unix timestamp that tells when it was created.
	2. **modified_at**: Unix timestamp that tells when it was last modified.
	3. **accessed_at**: Unix timestamp that tells when it was last accessed.
	4. **size**: The collective size of all the nodes inside the item being queried.
	5. **checksum**: The checksum that verifies file integrity.
	6. **chunks**: Pointer to chunks that contain file data.
3. A file stored in the filesystem should be split into 1 MB chunks.
4. Each file node should contain a pointer to the file chunks stored.

*Note: This exercise will take a lot of time, don't worry and be patient, it seems hard at first but it will become simple as you write the code.*

## 6. Algorithms
Several algorithms are interesting to learn and understand the techniques they use to solve the problem, There is a list of algorithms that you should know about and how they work

1. Huffman coding
2. RSA
3. DES
4. SHA (2 family)
5. Merge and Quicksort
6. Quick select
7. Kadane’s Algorithm
8. Boyer–Moore Majority Vote
9. Floyd’s Cycle Detection
10. KPM

These 10 are enough to give you the essence of algorithms, why they are designed the way they are, what purpose they serve, and how you can design your own when required.

### Exercise
1. Implement a spell checker that sources EN-US dictionaries and suggests words that the user may have indented but spelt wrong. Eg `kiten` may be corrected to `kitten` or `kite` [1]
2. Implement a compiler for *BrainFuck* language, probably including a memory layout visualizer [2]
3. Implement a code formatter for C language. [3]

[1] https://towardsdatascience.com/spelling-correction-how-to-make-an-accurate-and-fast-corrector-dc6d0bcbba5f
[2] https://onestepcode.com/brainfuck-compiler-c/
[3] https://journal.stuffwithstuff.com/2015/09/08/the-hardest-program-ive-ever-written/

---

This marks the end of your journey, or I must say, a new journey in computer science.

----
