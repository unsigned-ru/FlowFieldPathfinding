# FlowFieldPathfinding
> Researching an alternative to AI pathfinding for large amounts of agents.

## What is flowfield pathfinding
Flowfield pathfinding, sometimes also called Goal-Based Vector Field Pathfinding, generates a flowfield once per target position. Any agent can use the generated flowfield to "flow" towards the target position from anywhere that the flow field reaches.

## What is a flowfield?
A flowfield concists of cells, each cell holding a vector that points to their neigboring node that is closest to the target position. In code we represent this as a 2d grid (array) of vectors.

![Image](https://leifnode.com/wp-content/uploads/2013/12/ProjectTemplate-2013-12-05-10-25-33-59.jpg)

### Flowfield Pathfinding is achieved with 3 key steps:

  1. A cost field is generated that determines the cost between the goal and every tile/node on the map.
  2. A vector field that designates the direction to go in to reach the goal is generated.
  3. An agent queries the vector field for a direction to move towards according to its current position.
 
Whenever we request a new target position, the flowfield algorithm has to generate a new flowfield for that target position.

## A* vs flowfield pathfinding
A* pathfinding is very good at calculating the shortest path for **one agent seeking a goal**. But once you start having hundreds of agents seeking the same target there are more efficient solutions! Flowfield pathfinding attempts to solve that problem. Instead of calculating the path **agent based** it gets calculated **goal based**.

Both techniques can be combined to achieve efficient overall pathfinding.

### Pros:
  - Very efficient if you have many agents, seeking one goal.
  - Can be combined with other pathfinding techniques to suit certain areas.
  - Can be combined with interesting steering behaviors
  
### Cons:
  - Inneficient for big maps
  - Having many goals causes CPU strain.

## Sources:
https://leifnode.com/2013/12/flow-field-pathfinding/

https://www.jdxdev.com/blog/2020/05/03/flowfields/

https://gamedevelopment.tutsplus.com/tutorials/understanding-goal-based-vector-field-pathfinding--gamedev-9007
