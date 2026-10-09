Slip 9 
 
 Q1) A.Write a program to create a DataFrame which contains a person name 
and age ,Sort a DataFrame in ascending order of Age                                                                          
[10 marks]

```py
import pandas as pd 
 
# Create DataFrame 
data = { 
    'Person Name': ['Rahul', 'Sneha', 'Amit', 
'Priya', 'Karan'], 
    'Age': [25, 20, 30, 22, 27] 
} 
 
df = pd.DataFrame(data) 
 
print("Original DataFrame:") 
print(df) 
 
# Sort DataFrame by Age in ascending order 
sorted_df = df.sort_values(by='Age', ascending=True) 
 
print("\nDataFrame Sorted by Age:") 
print(sorted_df) 
``` 

Q2)B.Write a program to implement the Blocks World Problem. Represent the 
initial and goal states of a set of blocks, perform valid block movements 
according to the problem constraints and display each intermediate state until 
the goal configuration is achieved.                                         
[20 marks] 

```py
# Blocks World Problem 
def display_state(state): 
print("State:") 
for block, position in state.items(): 
print(block, "->", position) 
print() 
# Initial State 
initial_state = { 
'A': 'Table', 
'B': 'A', 
'C': 'Table' 
} 
# Goal State 
goal_state = { 
'A': 'Table', 
'B': 'C', 
'C': 'Table' 
} 
print("Initial State:") 
display_state(initial_state) 
# Move B from A to Table 
print("Move 1: Move B from A to Table") 
initial_state['B'] = 'Table' 
display_state(initial_state) 
# Move B from Table to C 
print("Move 2: Move B from Table to C") 
initial_state['B'] = 'C' 
display_state(initial_state) 
# Check goal state 
if initial_state == goal_state: 
print("Goal State Achieved!") 
else:
print("Goal State Not Achieved.")
```

OR 
Q2) B.Write a python program to compare BFS and DFS performance for graph 
search problems. 

[20 marks]

```py 
from collections import deque 
import time 
# Graph represented using adjacency list 
graph = { 
'A': ['B', 'C'], 
'B': ['D', 'E'], 
'C': ['F', 'G'], 
'D': ['H'], 
'E': [], 
'F': [], 
'G': ['I'], 
'H': [], 
'I': [] 
} 
# Breadth First Search 
def bfs(graph, start): 
visited = set() 
queue = deque([start]) 
order = [] 
while queue: 
vertex = queue.popleft() 
if vertex not in visited: 
visited.add(vertex) 
order.append(vertex) 
for neighbour in graph[vertex]: 
if neighbour not in visited: 
queue.append(neighbour) 
return order 
# Depth First Search 
def dfs(graph, start): 
visited = set() 
stack = [start] 
order = [] 
while stack: 
vertex = stack.pop() 
if vertex not in visited: 
visited.add(vertex) 
order.append(vertex) 
# Reverse order to maintain left-to-right 
traversal 
for neighbour in reversed(graph[vertex]): 
if neighbour not in visited: 
stack.append(neighbour) 
return order 
source = input("Enter source vertex (A-I): ").upper() 
if source not in graph: 
print("Invalid source vertex.") 
else: 
# Measure BFS performance 
start_time = time.perf_counter() 
bfs_result = bfs(graph, source) 
bfs_time = time.perf_counter() - start_time 
# Measure DFS performance 
start_time = time.perf_counter() 
dfs_result = dfs(graph, source) 
dfs_time = time.perf_counter() - start_time 
print("\nBFS Traversal:", " -> 
".join(bfs_result)) 
print("BFS Time:", format(bfs_time, ".8f"), 
"seconds") 
print("\nDFS Traversal:", " -> 
".join(dfs_result)) 
print("DFS Time:", format(dfs_time, ".8f"), 
"seconds") 
print("\nPerformance Comparison") 
print("----------------------") 
print("BFS Visited Nodes:", len(bfs_result)) 
print("DFS Visited Nodes:", len(dfs_result)) 
```

