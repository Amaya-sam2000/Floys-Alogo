# Floys-Alogo
Floyd algorithm to use recursion

import sys

NO_PATH = sys.maxsize
graph = [
    [0, 7, NO_PATH, 8],
    [NO_PATH, 0, 5, NO_PATH],
    [NO_PATH, NO_PATH, 0, 2],
    [NO_PATH, NO_PATH, NO_PATH, 0]
]

MAX_LENGTH = len(graph)

def floyd_iterative(distance, k=0, i=0, j=0):
    if k == MAX_LENGTH:
        print_matrix(distance)
        return

    if i == MAX_LENGTH:
        floyd_iterative(distance, k + 1, 0, 0)
        return

    if j == MAX_LENGTH:
        floyd_iterative(distance, k, i + 1, 0)
        return

    if distance[i][k] != NO_PATH and distance[k][j] != NO_PATH:
        new_distance = distance[i][k] + distance[k][j]
        if distance[i][j] > new_distance:
            distance[i][j] = new_distance

    floyd_iterative(distance, k, i, j + 1)

def print_matrix(matrix):
    for row in matrix:
        print(["INF" if val == NO_PATH else val for val in row])

floyd_iterative(graph)
Result
[0, 7, 12, 8]
['INF', 0, 5, 7]
['INF', 'INF', 0, 2]
['INF', 'INF', 'INF', 0]

Install requiremnt.txt in PyCharm 

Running both iterative and recursive for the comparison 
