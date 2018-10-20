Describe the fixes/improvements you made to the Graph implementation here.

1. add_edge()
   def add_edge(self, start, end, bidirectional=True):
   self.vertices[start].add(end)
   if bidirectional:
   self.vertices[end].add(start)

2. dfs

   def dfs(self, start, target=None):
   visited = []
   stack = Stack()
   stack.push(start)
   while stack.size() > 0:
   current = stack.pop()
   if current not in visited:
   if current == target:
   break
   visited.append(current)
   for next_vert in self.vertices[current]:
   stack.push(next_vert)
   return visited
