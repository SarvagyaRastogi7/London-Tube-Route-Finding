# London Tube Route-Finding Algorithms

## Overview

This repository contains Python implementations of classical AI search algorithms for finding routes on the London Tube map. The project uses real tube connection data and provides multiple algorithms for comparing path-finding strategies in terms of both efficiency and travel cost.

---

## Contents

- `London_Tube_Search.py`: Main Python script implementing all search algorithms.
- `tubedata.csv`: London Tube map data (station connections, lines, travel times, zones).
- `Report.pdf`: Written report with algorithm analysis, results, and answers to coursework questions.
- `CW1_23Oct2024.pdf`: Coursework brief and instructions.

---

## Data

- **`tubedata.csv`** contains the tube map as rows of:
```
[StartingStation], [EndingStation], [TubeLine], [AverageTimeTaken], [MainZone], [SecondaryZone]
```
- **StartingStation**: Name of the departure station.
- **EndingStation**: Name of the directly connected station.
- **TubeLine**: Name of the connecting tube line.
- **AverageTimeTaken**: Average travel time (minutes).
- **MainZone**: Main fare zone of the starting station.
- **SecondaryZone**: Secondary fare zone (or 0 if not applicable).

---

## Implemented Algorithms

All algorithms are implemented in `London_Tube_Search.py` and operate on the tube data loaded into Python via pandas.

- _**Breadth-First Search (BFS):**_
- Finds the shortest path in terms of number of stations.
- Returns the path, visited stations, and total travel time.

- _**Depth-First Search (DFS):**_
- Explores as far as possible along branches before backtracking.
- Returns the path, visited stations, and total travel time.

- _**Uniform Cost Search (UCS):**_
- Finds the lowest-cost path based on actual travel times.
- Returns the path, visited stations, and total travel time.

- _**UCS with Line Change Cost:**_
- Like UCS, but adds a 10-minute penalty for every tube line change.
- Returns the path, visited stations, and total travel time.

- _**Heuristic Best-First Search:**_
- Uses zone information as a heuristic to guide the search.
- Returns the path, visited stations, and total travel time.

- _**Visited Node Counter:**_
- Counts the number of unique stations visited during a search.

- _**Travel Cost Calculator:**_
- Computes total travel cost for a given path.

---

## How to Run

1. **Requirements:**  
 - Python 3.x
 - `pandas` library

2. **Usage:**  
 Place `London_Tube_Search.py` and `tubedata.csv` in the same directory.

 Run the script:
```
python London_Tube_Search.py
```
The script will:
- Load the tube data
- Build the station and zone dictionaries
- Run and print results for several test routes using all algorithms

---

## Example Output

For each tested route (e.g., "Canada Water" to "Stratford"), the script prints:
- The path found by each algorithm
- Number of visited nodes
- Total travel cost

Example table from the report:

| Route                          | BFS | DFS | UCS | UCS_Cost | Heuristic_BFS |
|---------------------------------|-----|-----|-----|----------|---------------|
| Canada Water → Stratford        | 52  | 52  | 51  | 10       | 46            |
| Ealing Broadway → South Kensington | 53 | 22 | 48 | 18       | 58            |

---

## Analysis & Report

See `Report.pdf` for:
- Detailed explanation of each algorithm
- Plots and tables comparing node visits and travel costs
- Discussion of algorithm strengths, weaknesses, and implementation challenges
- The longest route found without repeated nodes

---


**Author:** Sarvagya Rastogi (ec24781)

