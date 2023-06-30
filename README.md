#### topological-sort
topological sort; directed graph

A topological sort of a directed graph is a linear ordering of its vertices such that for every directed edge (u, v) from vertex u to vertex v, u comes before v in the ordering.

An algorithm for computing a topological sort finds many applications. For instance, the vertices of the graph may represent a project consisting of a number of tasks, and the edges may represent constraints that one task must be done before another, where each node is a task; in this application, a topological ordering is just a valid execution sequence of the project. A directed graph has at least one topological sort if and only if the graph has no directed cycles, i.e. the graph is a directed acyclic graph (DAG).

This code is an implementation of the following algorithm that can be used to compute a topological sort for a directed graph if it is acyclic and output a message indicating that the graph is not acyclic.

```
L ← Empty list, which will contain the sorted elements
S ← Set of all nodes with no incoming edge

  while S is not empty do
    remove a node n from S
    add n to tail of L
      for each node m with an edge e from n to m do
        remove edge e from the graph
        if m has no other incoming edges then
          insert m into S

if graph has edges then
  return “graph has at least one cycle” in the output file
else
  return L (a topologically sort) in the output file
```
