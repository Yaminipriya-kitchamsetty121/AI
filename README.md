8 Queens problem:
Algorithm:
1. Create an 8x8 chessboard. Start with the first row and no queens placed on the board for each column in the current row, try to place a queen.
2. For each placement, check if placing a queen in the current column of the current row is valid.
->The column should not already have a queen.
->No queens should be on the same diagonal (both major and minor).
3. If the placement is valid, move to the next row and repeat the process.
4. Recursively attempt to place a queen in each column of the next row.
5. If placing a queen in any column of the current row does not lead to a solution, remove the queen and try to the next column.
6. If no column is valid, return to the previous row and move the queen placed there to the next column.
7. If queens are successfully placed in all 8 rows, a solution is found.
8. Continue the process until all possible placements are tried or a solution is found.
![8 queens AI](https://github.com/user-attachments/assets/6f199de9-75e1-43ee-bb54-a5ac9a9a5259)




Water Jug Problem:
Algorithm:
1. Define a state by the amount of water in both jugs (x, y), where x is the amount of water in jug A    and y is the amount of water in jug B. 
2. Initialize the starting state (0, 0) and mark it as visited.
3. Use a queue to perform BFS. Enqueue the initial state (0, 0) and an empty path list to keep track of steps.
4. Dequeue the current state and path.
5. If either jug contains the target amount t, print the path and return.
6. For each operation (fill, empty, pour), generate new states and add them to the queue if they haven’t been visited before:
a.	Fill Jug A: (a, y)
b.	Fill Jug B: (x, b)
c.	Empty Jug A: (0, y)
d.	Empty Jug B: (x, 0)
e.	Pour Jug A to Jug B: Calculate the new state based on how much can be poured.
f.	Pour Jug B to Jug A: Similarly, calculate the new state.
7. Maintain a set to keep track of visited states to avoid processing the same state multiple times.
8. If the queue becomes empty without finding a solution, print that no solution exists.
![water jug AI](https://github.com/user-attachments/assets/c2f5b7a6-4578-405d-bf69-081c58bcbbba)





Crypto arithmetic:
Algorithm:
1. Identify the given equation and the letters that represent digits. For example, in the equation SEND + MORE = MONEY, each letter represents a unique digit (0-9).
2. Each letter must represent a unique digit.
3. The first letter in any number cannot be zero.
4. List all the unique letters involved in the puzzle.
5. Convert the word equation into a numerical equation where each letter is a variable.
6. Try all possible combinations of digits for the letters. This is practical only for simpler puzzles or with a computational approach.
7. Assign digits based on constraints. For instance, if a letter appears in the leading position, it can’t be zero. Test different digit assignments and check if they satisfy the equation.
8. Substitute the digits into the original equation to see if it holds true. Ensure that all digits are unique and follow the puzzle’s constraints.
9. If the trial doesn’t work, adjust the digit assignments and try again keep refining the approach based on results and logical deductions.
10. Once you find a solution, verify it by substituting all letters with their corresponding digits in the original equation ensure that there are no violations of constraints.
 ![crypto arithmetic](https://github.com/user-attachments/assets/cab760ab-37da-420f-9e6e-d6faca8c4fd8)





Breadth first search:
Algorithm:
1. Create an empty set visited to keep track of visited nodes.
2. Use a deque from the collections module as the queue to efficiently pop elements from the front.
3. Initialize traversal_ order to store the order of nodes visited.
4. Add the starting node to the queue and mark it as visited.
5. While the queue is not empty, dequeue a node from the front.
6. If this node hasn't been visited mark it as visited and add it to traversal_ order. Enqueue all its unvisited neighbours.
7.Return the traversal_ order list, which contains nodes in the order they were visited.
![BFS AI](https://github.com/user-attachments/assets/4f752913-e7f3-4b3f-93ce-d4b7ee2b7fcc)





Depth first Search:
Algorithm:
1. Create an empty set visited to keep track of visited nodes.
2. Create an empty list traversal_order to store the order of nodes visited.
3. Mark node as visited append node to traversal_ order recursively call dfs for each neighbor of node that hasn't been visited.
4. Call dfs(start) to begin the traversal from the start node. Return the traversal_ order list.
5. Create an empty set visited to keep track of visited nodes.
6. Initialize a stack with the start node to create an empty list traversal_ order to store the order of nodes visited. While the stack is not empty:
	Pop a node from the stack.
	If the node is not in visited:
7. Mark it as visited. Append it to traversal_ order. Push all unvisited neighbors of the node onto the stack .
8. Return the traversal_order list.
![DFS AI](https://github.com/user-attachments/assets/d5788872-38e5-48cf-a0b4-b386f2349ca1)






A*
Algorithm:
1. Start at a given position on the grid.
2. If the current cell is dirty, clean it.
3. Choose the next cell to move to. Options include:
4. Move to the nearest dirty cell.
5. Move in a specific pattern (e.g., zig-zag) to ensure coverage.
6. Use a combination of both strategies for optimal cleaning.
7. Move the vacuum cleaner to the chosen cell.
8. Go back to step 2 until all cells are clean.
![A AI](https://github.com/user-attachments/assets/69d8a911-446f-48cc-a639-573ce9fecf1a)





Map colouring:
Algorithm:
1.Start from the initial node and enqueue it into the queue.
2.While the queue is not empty, dequeue a node and process it.
3.Enqueue all unvisited neighbors of the dequeued node.
4.Repeat steps 2 and 3 until the queue is empty.
![map coluring](https://github.com/user-attachments/assets/0be5e258-7236-4167-a798-299b896755f1)




