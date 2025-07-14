# Floys-Alogo
Floyd algorithm to use recursion
### Running the scripts ###
import sys
import itertools

NO_PATH = sys.maxsize

graph = [
    [0, 7, NO_PATH, 8],
    [NO_PATH, 0, 5, NO_PATH],
    [NO_PATH, NO_PATH, 0, 2],
    [NO_PATH, NO_PATH, NO_PATH, 0]
]

n = len(graph)

def floyd_iterative(distance):
    # itertools.product generates all combinations of k, i, j in range(n)
    for k, i, j in itertools.product(range(n), repeat=3):
        if distance[i][k] != NO_PATH and distance[k][j] != NO_PATH:
            new_distance = distance[i][k] + distance[k][j]
            if distance[i][j] > new_distance:
                distance[i][j] = new_distance

def print_matrix(matrix):
    for row in matrix:
        print(['INF' if val == NO_PATH else val for val in row])

floyd_iterative(graph)
print_matrix(graph)

Result
[0, 7, 12, 8]
['INF', 0, 5, 7]
['INF', 'INF', 0, 2]
['INF', 'INF', 'INF', 0]
### How do I get set up? ###
Install requiremnt.txt 
### Requirements ### 
blinker==1.9.0
click==8.2.1
Flask==3.1.1
itsdangerous==2.2.0
Jinja2==3.1.6
MarkupSafe==3.0.2
numpy==2.3.1
pandas==2.3.1
python-dateutil==2.9.0.post0
pytz==2025.2
six==1.17.0
tzdata==2025.2
Werkzeug==3.1.3

