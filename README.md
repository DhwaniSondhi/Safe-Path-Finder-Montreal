# Safe-Path-Finder-Montreal
This application aims to draw an optimal path on a map ignoring the high crime rate areas of Montreal downtown for the given dataset.

## Inputs
- **"crime_dt.shp" file**: Crime data considered at different points for Montreal downtown. 
- **Grid size**: To define the grid cell size(like 0.002 or 0.003).
- **Threshold value**: To define high and low crime rate areas.

## How to run?
- Set up an environment and install the libraries: [heapq](https://docs.python.org/2/library/heapq.html), [shapely](https://shapely.readthedocs.io/en/stable/manual.html), [geopandas](http://geopandas.org/), [pandas](https://pypi.org/project/pandas/), [matplotlib](https://matplotlib.org/) and [numpy](https://numpy.org/).
- Open a new [Jupyter notebook](https://jupyter.org/) and paste the code.
- Keep the related files like 'crime_dt.shp' and other related files in the folder you are working in.
- Run the code.

## Working
The "crime_dt.shp" file and the input grid size is used to generate grids accumulated using statistics such as total count, mean or standard deviation. Depending on the given threshold, we define the high(YELLOW) and low(BLUE) crime rate blocks. Following are the maps created with various threshold values:
![](https://github.com/DhwaniSondhi/Safe-Path-Finder-Montreal/blob/master/docs/images/thresholdmaps.PNG)
Further, heuristic algorithms like [A* algorithm](https://en.wikipedia.org/wiki/A*_search_algorithm) and [Best-first search algorithm](https://en.wikipedia.org/wiki/Best-first_search) are implemented and compared to study their efficiency in finding the optimal path from one end to another avoiding entry in high crime rate areas.
Following ***heuristic function*** is used which takes the x value as the x coordinate and y as y coordinate of the present(node)/goal grid cell:
```python
heuristicValue(node) = max{abs(node.x - goal.x), abs(node.y - goal.y)} 
```
## Outputs
Following are the maps with optimal paths generated for each algorithm where the A* algorithm has shown better efficiency.
### Best First Search algorithm
<img src="https://github.com/DhwaniSondhi/Safe-Path-Finder-Montreal/blob/master/docs/images/best-first%20search.PNG" width="650" height="375" />

### A* algorithm
<img src="https://github.com/DhwaniSondhi/Safe-Path-Finder-Montreal/blob/master/docs/images/a%20algorithm.PNG" width="650" height="375" />

**[Further detailed description of the project](https://github.com/DhwaniSondhi/Safe-Path-Finder-Montreal/blob/master/docs/Project%20Report.pdf)**
