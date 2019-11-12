#input readers
# cases

cases = int(input())
for i in range(cases):
    #code

# while not 0 0
line = input()
endString = "0 0"
while line != endString:
    #code
    line = input()

#until end of file
import sys
for line in sys.stdin:
    line = line.strip() #remove those pesky newline characters
    #code

#assign numbers on line to ints
a, b, c = map(int, input().split(" "))



#bfs
def generateOptions(origin):
    result = []
    #add options to result
    return result


start = "" #starting value
goal = "goal" #goal value
fromMap = {start:start}
used = set()
while goal not in fromMap:
    currentList = [x for x in fromMap if x not in used]
    for item in currentList:
        for subItem in generateOptions(item):
            if subItem not in fromMap:
                fromMap[subItem] = item
        used.add(item)
path = [goal]
current = goal
while current != start:
    current = fromMap[current]
    path.append(current)
path.reverse() # gives you the final path to finding the shortest way to goal



#dijkstra

from collections import defaultdict
class Graph:
  def __init__(self):
    self.nodes = set()
    self.edges = defaultdict(list)
    self.distances = {}

  def add_node(self, value):
    self.nodes.add(value)

  def add_edge(self, from_node, to_node, distance):
    self.edges[from_node].append(to_node)
    self.edges[to_node].append(from_node)
    self.distances[(from_node, to_node)] = distance

import math
def dijsktra(graph, initial):
  visited = {initial: 0}
  path = {}
  nodes = set(graph.nodes)

  while nodes:
    min_node = min(nodes, key= lambda x: visited.get(x, math.inf))
    if min_node is None: break
    nodes.remove(min_node)
    current_weight = visited[min_node]

    for edge in graph.edges[min_node]:
      weight = current_weight + graph.distances[(min_node, edge)]
      if edge not in visited or weight < visited[edge]:
        visited[edge] = weight
        path[edge] = min_node

  return visited, path
