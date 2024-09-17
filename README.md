![8 queens AI](https://github.com/user-attachments/assets/6f199de9-75e1-43ee-bb54-a5ac9a9a5259)8 Queens problem:
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


Breadth first search:
Algorithm:
1. Create an empty set visited to keep track of visited nodes.
2. Use a deque from the collections module as the queue to efficiently pop elements from the front.
3. Initialize traversal_ order to store the order of nodes visited.
4. Add the starting node to the queue and mark it as visited.
5. While the queue is not empty, dequeue a node from the front.
6. If this node hasn't been visited mark it as visited and add it to traversal_ order. Enqueue all its unvisited neighbours.
7.Return the traversal_ order list, which contains nodes in the order they were visited.


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


A*
Alogorithm:
•	Create Open and Closed Sets:
o	Open Set: A priority queue or min-heap containing nodes to be evaluated, initialized with the start node.
o	Closed Set: A set of nodes that have already been evaluated.
•	Initialize Costs:
o	g_cost for each node: The cost from the start node to the current node.
o	f_cost for each node: The estimated total cost (g_cost + h_cost).
o	h_cost: The heuristic estimate from the current node to the goal node.
•	Set Start Node Costs:
o	g_cost of the start node to 0.
o	f_cost of the start node to its h_cost.
2.Algorithm Execution:
•	While the Open Set is not Empty:
1.	Select the Node with the Lowest f_cost:
	Dequeue the node with the lowest f_cost from the Open Set. This node is called current_node.
2.	Check for Goal:
	If current_node is the goal node, reconstruct the path from start to goal and return it.
3.	Move Node to Closed Set:
	Add current_node to the Closed Set.
4.	Evaluate Neighbors:
	For each neighbor of current_node:	If the Neighbor is in the Closed Set:
	Skip it as it has already been evaluated.
	Calculate Costs:
	Calculate the tentative g_cost (i.e., g_cost of current_node plus the cost to reach the neighbor).
	If the neighbor is not in the Open Set or the new g_cost is lower than its current g_cost:
	Update the g_cost and f_cost of the neighbor.
	Set the current_node as the parent of the neighbor (for path reconstruction).
	If the neighbor is not in the Open Set, add it to the Open Set.
5.	Continue Until Path is Found or Open Set is Empty:
	If the Open Set becomes empty without finding the goal, report that there is no path.
3.Path Reconstruction:
•	Once the goal node is reached, reconstruct the path from the start node to the goal node by following parent pointers from the goal node back to the start node.


Graph colouring:
Algorithm:
Create a data structure (e.g., a list) to store the color assigned to each node. Initially, no colors are assigned (e.g., all values are 0).
Choose the number of colors m to use for coloring the map
Create a function is_safe(node, color) that checks whether it is safe to assign a particular color to node.
The function ensures that none of the node’s neighbors (connected nodes) have the same color.
Backtracking Algorithm to Assign Colors
Start at the first node.
For each node, try assigning each color from 1 to m.
Check if the Color is Valid: Use the is_safe function to check whether the color can be assigned to the current node without conflict.
Recursive Call: If the color is valid, assign it to the node and recursively call the function for the next node.
Backtrack: If assigning a color to a node leads to a conflict later, reset the color of the current node (backtrack) and try a different color.
If all nodes are colored successfully, return the color assignments. If no solution is possible, backtrack to the previous node and try again.
The algorithm terminates when either:
All nodes are successfully assigned colors (in which case, a valid coloring is found).
No valid color assignments are possible, meaning the map cannot be colored with the given number of colors.



