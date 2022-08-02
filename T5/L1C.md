# This is notes for L1C

> Design goal: The programmer just need to send their tasks to the ACC without knowing how the ACC works, the ACC must be able to finish all the accelerate tasks.

# Notes for 2022.08.01

## PingPong Buffer

Ping Pong buffer is like binary buffer, but it's not binary buffer.

1. A binary buffer has two buffer, the first buffer and the second buffer. We only input data into the first buffer and output data from the second buffer. When the second buffer need data from the first buffer, we do a quick data transfer from the first buffer to the second buffer(this requires hardware support)

2. The ping buffer and pong buffer can all be used for data input and data output. If we want to write into the ping pong buffer, we must check which buffer is running the algorithm. If the ping buffer is running the algorithm, we write data into the pong buffer and the ping buffer is used to output the algorithm result; in the next write operation, we run algorithm on pong buffer because it contains new data, and we input data to ping buffer because it's data is already been used in the previous stage.

## Control Unit

> There are 2 kinds of control unit: Hardware & micro-programmed, (the difference of the two)[https://www.geeksforgeeks.org/computer-organization-hardwired-vs-micro-programmed-control-unit/]


## Questions

1. 配置下发是指使用config mem来配置acc的内部寄存器吗?

2. control加速器的关系是什么？配置寄存器是放在control里面的还是放在加速器里面的?

3. config mem和config mem ping/pong的关系是什么?

4. Task的格式是什么： addr和reg的含义是什么？
