# Flood Fill

## Initial Solution

On first look, we can model this problem as a graph. As such, we could use DFS or BFS to solve it. In each iteration, we add the four children (four cardinal directions) to the frontier.

There is no need to keep track of the visited states (i.e. graph search), as we know that a state has been visited if its value has been changed to the intended colour.

Time Complexity: O(4^mn)
Space Complexity: O(mn)

Where m and n are the row and column length respectively.

```python
def floodFill(self, image, sr, sc, color):
  frontier = []
  frontier.append([sr, sc])
  row, col = len(image) - 1, len(image[0]) - 1
  value = image[sr][sc]

  while frontier:
      x, y = frontier.pop()
      if x < 0 or y < 0 or x > row or y > col or image[x][y] == color or image[x][y] != value:
          continue
          
      image[x][y] = color
      children = [[x-1, y], [x+1, y], [x, y-1], [x, y+1]]
      frontier += children

  return image
```

Completed: 8/10/2023
