PYTHON PROGRAMS:
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
    ->Pop a node from the stack.
    ->If the node is not in visited:
7. Mark it as visited. Append it to traversal_ order. Push all unvisited neighbors of the node onto the stack .
8. Return the traversal_order list.
![DFS AI](https://github.com/user-attachments/assets/d5788872-38e5-48cf-a0b4-b386f2349ca1)









A*:
Algorithm:
1. Initialize the Open Set with the start node and the Closed Set as empty.
2. Loop until the Open Set is empty or the goal is found:
3. Get the node with the lowest f value from the Open Set.
4. If it's the goal, reconstruct and return the path.
5. Otherwise, move it to the Closed Set.
6. For each neighbour, calculate the g, h, and f values, and update as needed.
7. Return the path if the goal is reached, otherwise indicate that no path exists.
![A AI](https://github.com/user-attachments/assets/69d8a911-446f-48cc-a639-573ce9fecf1a)










Map colouring:
Algorithm:
1. Define the number of colours available 
2. Create a graph representation of the map using an adjacency list or matrix.
3. Initialize a list or array to store the colours assigned to each region.
4. Define a function is_ safe that checks if assigning a given colour to a node is valid:
                    ->For each adjacent node of the current node, check if any have the same colour.
                    ->If any adjacent node has the same colour, return False. Otherwise, return True.
5. Define a recursive function map_ colouring that:
1.	Base Case:
       ->	If all nodes have been assigned a colour, return True (solution found).
2.	Try Different Colours:
   For each colour from 1 to m:
1.	Check if assigning the current colour to the current node is valid using is_safe(node, colour).
2.	If valid:
        a.	Assign the colour to the current node.
        b.	Recursively call map_ colouring, where next_ node is the next uncoloured node.
        c.	If the recursive call returns True, propagate that result back up.
        d.	If not, backtrack by removing the colour assignment 
4. Driver Function
      1. Define a function solve_ map_ colouring that:
            a.Initialize the colour list.
            b.Call map_ colouring where start_ node is the first region of the map.
            c.If the call returns True, print the colours assigned to each node; otherwise, print that no solution exists.
![map coluring](https://github.com/user-attachments/assets/0be5e258-7236-4167-a798-299b896755f1)











Travelling Salesman problem:
Algorithm:
1. Initialization
  ->	Create a list or matrix to represent the distances between cities.
  ->Initialize a variable to store the minimum cost (or distance).
  ->Create a path list to keep track of the current path.
2. Backtracking Function
       1.	Define a recursive function tsp (current_city, visited, path, current_cost) that:
Base Case:
   ->If all cities have been visited, add the cost to return to the starting city. If this cost is less than the current minimum, update the minimum cost and the best path.
Recursive Case:
     ->	For each city, if it hasn't been visited:
     ->	Mark it as visited.
     ->	Add the cost to reach this city to the current cost.
     ->	Add this city to the current path.
     ->	Recursively call tsp for the next city.
     -> Backtrack by unmarking the city and removing it from the current path.
3. Driver Function
          1. Define a function solve_ tsp(distances) that:
                            a. Initialize the visited list, path, and current cost.
                            b. Call the backtracking function starting from the first city.
                            c. Print the minimum cost and the best path found.

![tsp AI](https://github.com/user-attachments/assets/2cb2ff91-bbd4-4c2d-8b8b-d3047a62f637)











Tic_Tac-Toe:
Algorithm:
1. Initialize the game board (3x3 grid) with empty spaces.
2. Create a loop to alternate between players' turns until the game ends.
3. Display the current game board.
4. Prompt the current player for their move (row and column).
5. Check if the selected cell is empty. If not, ask the player to choose again.
6. Update the selected cell with the player's symbol (X or O).
7. Check for a win condition: 3 symbols in a row, column, or diagonal.
8. If a win is detected, declare the current player as the winner.
9. If the board is full and no win is detected, declare a tie.
10. End the game loop.
![TTT AI](https://github.com/user-attachments/assets/7220e82f-ff61-49ea-a23e-daed3239f5fb)













Decision Tree:
Alogorithm:
1.start the program.
2. To divide the data based on target variables, choose the best feature employing Attribute   Selection Measures (ASM).
3. Then it will divide the dataset into smaller sub-datasets and designate that feature as a decision node for that branch.
4. Once one of the conditions matches, the procedure is repeated recursively for every child node to begin creating the tree.
5. The identical property value applies to each of the tuples.
               ->There aren't any more qualities left.
                ->There aren't any more occurrences.
![DT AI](https://github.com/user-attachments/assets/2616b053-a762-4c0e-82f5-4cac9fe8b365)













Alpha,Beta:
Algorithm:
1.Initialization:
  ->	Set two values, alpha and beta. Alpha is the best value that the maximizer currently can guarantee at that level or above (initially set to negative infinity). Beta is the best value that the minimizer currently can guarantee at that level or above (initially set to positive infinity).
2.Recursive Search:
   ->	Traverse the tree recursively, alternating between maximizing and minimizing players.
   -> At each node:
1.	If the node is a maximizing node:
->Update alpha with the maximum value between alpha and the value of the current node.
->If alpha is greater than or equal to beta, prune the remaining branches (return the value).
2.If the node is a minimizing node:
->Update beta with the minimum value between beta and the value of the current node.
->If beta is less than or equal to alpha, prune the remaining branches (return the value).
3.Return the Value:
 ->	Once all nodes are evaluated, return the optimal value for the player at the root node.
![alpha beta](https://github.com/user-attachments/assets/7e72ddaf-b37b-4ec1-94a4-d34865114c01)












Feed Forward Netrual Network:
Algorithm:
1. start the program 
2. The input layer comprises neurons that receive input.
3. The hidden layer contains a large number of neurons that modify the inputs and interact with the output layer.
4. The output layer contains the result of the computation.
![FFNN AI](https://github.com/user-attachments/assets/7ab6ffa7-8efd-4cf3-8128-19e0cd839cf9)













8 Puzzle:
Algorithm:
1. Represent the puzzle as a 3x3 grid, where each cell contains a number (1-8) or is empty (0).
2. Each node in the search tree represents a state of the puzzle. It contains the current state, the previous state (parent), the move that led to this state, and the cost (usually the sum of the path cost and a heuristic estimate).
 3. Choose a heuristic function that estimates the cost from the current state to the goal state. A common heuristic for the 8-puzzle is the Manhattan distance, which is the sum of the horizontal and vertical distances of each tile to its correct position.
4.  Use a priority queue (e.g., a min-heap) to store nodes during the search. Nodes are dequeued based on their total cost (p222ath cost + heuristic cost).
5. a. Initialize the priority queue with the initial state. 
    b. While the priority queue is not empty:
                    i. Dequeue the node with the lowest total cost.
                    ii. If the current state is the goal state, the solution is found.
                    iii. Generate successor states by moving the empty space in all possible directions (up, down, left, right). 
                      iv. For each successor state: - Calculate the cost (path cost + heuristic cost).
6.Once the goal state is reached, follow the parent pointers from the goal node to the initial node to extract the sequence of moves that lead to the solution.
![8 puzzle AI](https://github.com/user-attachments/assets/d9c65fb9-e488-4f83-85c9-61379e6e4d01)














Missionaries:
Algorithm:
1. One way to solve the Missionaries and Cannibals problem is to use a variation of the Breadth-First Search (BFS) algorithm.
2. The idea is to represent the states of the problem (the number of missionaries and cannibals on each side of the river and the boat's location) as nodes in a graph.
3. Then, by systematically exploring the graph using BFS, you can find a valid sequence of moves that solves the problem.
![missionaries AI](https://github.com/user-attachments/assets/b35a0d1e-52ed-4989-8ef3-a5a1dddbfc19)











Vacuum Cleaner:
Algorithm:
1. Start at a given position on the grid.
2. If the current cell is dirty, clean it.
3. Choose the next cell to move to. Options include:
4. Move to the nearest dirty cell.
5. Move in a specific pattern (e.g., zig-zag) to ensure coverage.
6. Use a combination of both strategies for optimal cleaning.
7. Move the vacuum cleaner to the chosen cell.
8. Go back to step 2 until all cells are clean.
![vaccum cleaner AI](https://github.com/user-attachments/assets/15dff980-d5bc-4bf1-9f77-57717d2ebc6d)










PROLOG PROGRAMS:
Sum the Integers:
Algorithm:
1. If the list is empty, return 0.
2. Split the list into the first element (head) and the rest of the list (tail).
3. Recursively call the sum function on the tail to get the sum of the remaining elements.
4. Add the head to the sum obtained from the tail.
5. Return the total sum.
![sum prolog AI](https://github.com/user-attachments/assets/7badc5b2-5705-4823-aa4b-6914b63737ee)












A DB program:
Algorithm:
% Define the database of names and DOBs
person('Alice', '1990-05-15').
person('Bob', '1985-07-22').
person('Charlie', '1992-11-30').
person('David', '1988-03-05').
person('Eve', '1995-12-10').
% Query the database
% dob/2: Finds the date of birth of a person.
% dob(+Name, -DOB)
dob(Name, DOB) :-
    person(Name, DOB).  % Look up the person's DOB in the database.
% Example usage:
% ?- dob('Alice', DOB).
% DOB = '1990-05-15'.
![DB AI](https://github.com/user-attachments/assets/4730c2f2-fbbf-4b42-b1be-f1b8b6966ac5)












Teacher_Student:
Algorithm:
% Define the database with facts
% student(Name, SubjectCode)
student('Alice', 'CS101').
student('Bob', 'CS102').
student('Charlie', 'CS101').
student('David', 'CS103').
student('Eve', 'CS102').
% teacher(Name, SubjectCode)
teacher('Prof. Smith', 'CS101').
teacher('Prof. Johnson', 'CS102').
teacher('Dr. Brown', 'CS103').
% Query to find all subjects a student is enrolled in
% student_subjects/2: finds all subject codes for a student
% student_subjects(+StudentName, -SubjectCode)
student_subjects(StudentName, SubjectCode) :-
    student(StudentName, SubjectCode).
% Query to find all subjects a teacher teaches
% teacher_subjects/2: finds all subject codes for a teacher
% teacher_subjects(+TeacherName, -SubjectCode)
teacher_subjects(TeacherName, SubjectCode) :-
    teacher(TeacherName, SubjectCode).
% Example usage:
% ?- student_subjects('Alice', SubjectCode).
% SubjectCode = 'CS101'.
% 
% ?- teacher_subjects('Prof. Johnson', SubjectCode).
% SubjectCode = 'CS102'.
![student prolog](https://github.com/user-attachments/assets/250ed56a-72bb-461b-b391-9579fa5c77dc)












Planets:
Algorithm:
% Database of planets with names, types, and distances from the sun
planet(mercury, rocky, 0.39).
planet(venus, rocky, 0.72).
planet(earth, rocky, 1.00).
planet(mars, rocky, 1.52).
planet(jupiter, gas_giant, 5.20).
planet(saturn, gas_giant, 9.58).
planet(uranus, gas_giant, 19.22).
planet(neptune, gas_giant, 30.05).
% Predicate to query planets of a specific type
planets_of_type(Type, Planets) :-
    findall(Name, planet(Name, Type, _), Planets).
% Predicate to query planets within a specific distance range
planets_within_distance(Min, Max, Planets) :-
    findall(Name, (planet(Name, _, Distance), Distance >= Min, Distance <= Max), Planets).
% Example queries
?- planets_of_type(rocky, RockyPlanets).
RockyPlanets = [mercury, venus, earth, mars].
?- planets_within_distance(5, 20, NearbyPlanets).
NearbyPlanets = [jupiter, saturn, uranus].
?- planet(Name, Type, Distance), Distance > 10.
Name = uranus,
Type = gas_giant,
Distance = 19.22 ;
Name = neptune,
Type = gas_giant,
Distance = 30.05.
![planets](https://github.com/user-attachments/assets/ea072db1-b240-4944-9ee5-63014908acc3)












Towers of Hanoi:
Algorithm:
1. The base case for solving the Towers of Hanoi with one disk is to directly move the disk from the source peg to the destination peg.
2. For `N` disks, we can recursively solve it by following these steps:
   - Move `N-1` disks from the source peg to the auxiliary peg, using the destination peg as the auxiliary.
   - Move the `N`-th disk from the source peg to the destination peg.
   - Move the `N-1` disks from the auxiliary peg to the destination peg, using the source peg as the auxiliary.
![tower](https://github.com/user-attachments/assets/ad6b0484-e558-4556-b91b-fc3094cc4d27)













Bird:
Algorithm:
1. Define a set of facts describing various bird species and their characteristics, including whether they can fly.
2. Create a predicate `can_fly/1` that checks if a given bird can fly based on its characteristics.
![bird](https://github.com/user-attachments/assets/eb62b969-da16-4d38-b6a6-00a30d203ae0)












Family tree:
Algorithm:
1. Define facts for individuals in the family with their relationships.
2. Define rules for different relationships like parent, child, and sibling.
3. Utilize the defined facts and rules to answer queries about the family relationships.
![family](https://github.com/user-attachments/assets/856419e1-b92e-423c-9e2f-77e82c12f1ea)










Diet:
Algorithm:
1. Define facts for various diseases and their corresponding dietary recommendations.
2. Create rules that suggest a diet based on the disease.
3. Utilize the facts and rules to answer queries about diet recommendations for specific diseases.
![diet](https://github.com/user-attachments/assets/9f9ba144-4e48-4122-ac58-06e41f7a1ce0)













MOnkey Problem Problem:
Algorithm:
1. Define the initial state of the monkey, banana, and box positions.
2. Define predicates for actions like `move`, `climb`, `push`, and `grasp` which change the state of the monkey and the box.
3. Create a predicate `solve` which specifies a sequence of actions to move the monkey to the banana and then to the box with the banana.
![monkey](https://github.com/user-attachments/assets/439d338f-3a15-4e6f-a262-eeffd37a10b5)











Fruit:
Algorithm:
1. Define facts about various fruits and their colors.
2. Use backtracking to query and retrieve the color of a specific fruit.
![fruit](https://github.com/user-attachments/assets/6f585875-0256-4178-b691-f84a4607987e)












BFS:
Algorithm:
1. Define facts for the graph's edges and their costs.
2. Implement the Best First Search algorithm using a priority queue.
   - Initialize an empty priority queue with the start node and its cost.
   - While the priority queue is not empty:
     - Pop the node with the lowest cost from the priority queue.
     - If the popped node is the goal node, return success.
     - Otherwise, expand the current node by generating its successors.
     - For each successor, calculate the cost and add it to the priority queue.
3. If the priority queue becomes empty without reaching the goal node, return failure.
![breadthfirstsearch](https://github.com/user-attachments/assets/506e6631-4d59-4b62-8793-97e5a993bbd2)













Disease:
Algorithm:
1. Define facts for symptoms and diseases. Each symptom is associated with one or more diseases.
2. Define rules to diagnose diseases based on symptoms.
3. Use backtracking to find all possible diseases that match the given symptoms.
![disease AI](https://github.com/user-attachments/assets/3cd75b82-2f45-49be-b735-aa79174c79c2)


