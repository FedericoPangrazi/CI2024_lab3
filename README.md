# CI2024_lab3
In this lab, the main difficulties were to find a proper heuristic function to feed the chosen approach in order to solve the n-puzzle. In my case, the selected approach was the **Greedy-best first algorithm**, which consist in expanding the node that has the best score coming out of the heuristic function. My idea was to define the heuristic function returned value based on *Manhattan distance*, but in order to make it more precise the *linear conflicts* quantity has been integrated. This quantity represents the number of couples of elements that are in the right row (or column) with respect to the goal state, but they are in the wrong coloumn (or row).
## Linear conflicts function
My linear conflict function maps first the elements in the goal state to their position, so in tuples (row,column), then uses that tuples to check if the elements are in the right positions or not, increasing the number of linear conflicts when found.
## Heuristc function
My heuristic function sums the value of the *Manhattan distance* of the state with the number of linear conflicts, multiplied by two because a linear conflict needs two more moves in order to be solved.
## Research function
First we define a Node with its attributes: state, parent, action and heuristic. In order to build the path from a starting state randomized with the teacher's funcion *do_action* , we define a *PriorityQueue* to store the nodes to be explored, and a set to store the nodes already explored. To get the successors of each state being explored, the teacher's function *available_actions* is called, and all the possible next states are stored in a list. For each of these next states, we then compute the heuristic and generate the next node to explore in the Priority Queue.
## Results
The implemented solution manages to solve the n-puzzle for the $3x3$ dimension in few seconds, the $4x4$ in one minute but the $5x5$ takes too much time to be solved, more than 2 hours. 
