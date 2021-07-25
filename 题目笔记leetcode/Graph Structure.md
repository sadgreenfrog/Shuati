Graph structure

```python
class Graph:
    '''
     This class is a example to help understand the logic and relation in a graph.
     The goal is to find all paths and shortest path between 2 location.
    '''
    def __init__(self, edges): # deges是node之间的关系
        self.edges = edges
        # Transfer tuple to better data structure, dictionary
        self.graph_dict = {}
        for start, end in self.edges:
            if start not in self.graph_dict:
                self.graph_dict[start] = [end] # End的括号一定要加上
            else:
                self.graph_dict[start].append(end)
        print("Graph Dictionary", self.graph_dict)

    def get_paths(self, start, end, path=[]):
        # Use recursion here. You can get the path backward from start to end.
        # Add path是因为CALL的时候，可以APPEND前面额parant进去
        # To think the simplest case first
        path = path + [start]
        if start == end:
            return [[path]]
        # Corner case: Guangzhou 不是出发点
        if start not in self.graph_dict:
            return []
        # Regular case:
        paths = [] # All possible paths
        for node in self.graph_dict[start]: # 遍历从起点开始的路线 前面PATH = []+ [START]
            if node not in path:
                # 这边调用GET_PATH, CHECK HOW MANY PATH FROM NODE TO NEWYORK
                new_paths = self.get_paths(node, end, path) # 找到终点会把PATH return进来, 也就是触发START = END的时候
                for p in new_paths: # 每次触发终点,就会一个一个加回来
                    paths.append(p)
        return paths

if __name__ == '__main__':
    routes = [
        ("Nanjing", "Zhenjiang"),
        ("Nanjing", "Shanghai"),
        ("Zhenjiang", "Beijing"),
        ("Zhenjiang", "Shanghai"),
        ("Shanghai", "Beijing"),
        ("Beijing", "Guangzhou"),
    ]

    route_graph = Graph(routes)
    start = "Nanjing"
    end = "Beijing"
    print(f"Paths between {start} and {end}:", route_graph.get_paths(start, end))
```
