# Maze-Solver
----------------------
Install pyamaze module
   pip install pyamaze


The code is in maze_solver.ipynb

These are the csv files of maze used for comparison, metrics of which are reported, please copy this files in the same directory as the notebook.
   - 30x30Maze.csv
   - 50x50Maze.csv
   - 70x70Maze.csv

For comparisons, I have created and saved the maze as csv files.
To execute the code on the saved mazes, run the notebook as it is, or else to generate maze with different size follow next.

------FOR SEARCH ALGORITHMS------
To generate random mazes with different sizes, please comment the following lines in class SearchAlgos __init__ method:
	self.m = maze()
        mazeFileName = f'{mazeSize[0]}x{mazeSize[1]}Maze.csv'
        self.m.CreateMaze(loadMaze=mazeFileName, theme='light')
and then uncomment the lines below which are in the same class below the lines we just commented above:
	#self.m = maze(mazeSize[0], mazeSize[1])
        #self.m.CreateMaze(loopPercent=50, saveMaze=True, theme = 'light')

and then execute the following for different algorithms, also you can specify the size of the maze to be generated:

--For BFS:

mazeSize = (30, 30) 
bfs = BFS(mazeSize=mazeSize)
bfs.startSearch()
bfs.algoStats("BFS",mazeSize)
bfs.m.run()

--For DFS:

mazeSize = (20, 20) 
dfs = DFS(mazeSize=mazeSize)
dfs.startSearch()
dfs.algoStats("DFS", mazeSize)
dfs.m.run()

--For A* Manhattan:

mazeSize = (40, 40) 
astar_manhat = AStar_Manhat(mazeSize=mazeSize)
astar_manhat.startSearch()
astar_manhat.algoStats('AStar_Manhat', mazeSize)
astar_manhat.m.run()

--For A* Euclidian:

mazeSize = (50, 50) 
astar_euc = AStar_Euclid(mazeSize=mazeSize)
astar_euc.startSearch()
astar_euc.algoStats('AStar_Euclid', mazeSize)
astar_euc.m.run()


------FOR MDP POLICY AND VALUE ITERATION------

To generate random mazes with different sizes in MDP, please comment the following lines in class MarkovDP __init__ method:
	self.maze = maze()
        mazeFileName = f'{mazeSize[0]}x{mazeSize[1]}Maze.csv'
        self.maze.CreateMaze(loadMaze=mazeFileName, theme='light')
		
and then uncomment the lines below which are in the same class below the lines we just commented above:
	#self.maze = maze(mazeSize[0], mazeSize[1])
        #self.maze.CreateMaze(loopPercent=50, saveMaze=True, theme = 'light')

and then execute the following for different algorithms, also you can specify the size of the maze to be generated:

--For MDP Value Iteration:

mazeSize = (45, 45) 
valueItr = MDP_ValueIter(mazeSize=mazeSize)
valueItr.startmdp_ValueIter()
valueItr.maze.run()

--For MDP Policy Iteration:

mazeSize = (40, 40) 
policyIter = MDP_PolicyIter(mazeSize=mazeSize)
policyIter.startmdp_PolicyIter()
policyIter.maze.run()

--------------------------------------------------------------------------------------
I am using pyamaze module to generate the maze in jupyter notebook. 
Whenever you run an instance of pyamaze for a particular maze size and algorithm, you may need to restart the kernel and execute again for another.
For executing different size and algorithm, please ensure that pyamaze environment is reset after execution by restarting the kernel. 
--------------------------------------------------------------------------------------
