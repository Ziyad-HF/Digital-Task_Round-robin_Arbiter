# Digital-Task_Round-robin_Arbiter

## Overview

The Round Robin Arbiter is a digital circuit developed using Verilog for arbitration in computer systems, particularly in scenarios where multiple requesters contend for access to a shared resource. This project aims to provide a fair and deterministic method for allocating access to the shared resource by rotating through a sequence of requesters and granting each requester access for a fixed time slice or priority level before moving on to the next requester.

## Purpose

The Round Robin Arbiter's primary purpose is to ensure equitable distribution of a shared resource among multiple competing requesters. It accomplishes this by implementing a rotating mechanism, granting access to each requester in a sequential order. This ensures that over time, each requester receives an equal share of the resource, promoting fairness and avoiding resource starvation.

> For the [circuit code](/round_robin.v) and its [test bench](/round_robin_tb.v)  

## Applications

The Round Robin Arbiter finds applications in various computer systems and scenarios:

1. **Bus Arbitration:** In computer systems with a shared bus architecture, the Round Robin Arbiter can be employed to allocate bus access fairly among multiple devices or modules. This prevents any single device from monopolizing the bus and ensures efficient resource utilization.

2. **Shared Memory Controllers:** In systems with shared memory, the Round Robin Arbiter can be used to allocate access to the memory among multiple requesting devices or processors. This is crucial for maintaining fairness and preventing memory contention, which can lead to performance bottlenecks.

3. **Task Scheduling:** Round Robin scheduling algorithms within operating systems can utilize Round Robin Arbiters to allocate CPU time among multiple processes or threads. This ensures that each task gets its fair share of CPU time, preventing any one task from dominating the system's processing resources.

## Circuit Operation

### Inputs

The Round Robin Arbiter takes the following inputs:

- `clk`: Clock signal.
- `rst`: Reset signal.
- `req`: A 4-bit input representing requests from up to four sources.

### Outputs

The Round Robin Arbiter provides the following output:

- `grant`: A 4-bit output representing the granted access to each source.

### Registers

The circuit includes two registers:

- `state`: A 3-bit register representing the current state of the arbiter.
- `next_state`: A 3-bit register representing the next state of the arbiter.

### Operation Details

The Round Robin Arbiter operates as follows:

1. Initialization: Upon startup or reset (`rst` signal), the arbiter initializes its state and begins in a predefined state.

2. Request Handling: Requests from various sources (`req`) are processed by the arbiter. When a new request arrives, it is added to the rotation queue.

3. Granting Access: The arbiter grants access to the current requester based on its internal state. This access is granted for a fixed time slice or priority level.

4. State Transition: After the requester's time slice expires or after the requester completes its operation, the arbiter advances to the next state in its sequence. This, in turn, selects the next requester to be granted access.

5. Fair Allocation: The rotation continues in a loop, ensuring that each requester eventually receives access to the shared resource. This mechanism guarantees fairness in resource allocation.


## Conclusion

The Round Robin Arbiter is a valuable component in computer systems where fair and deterministic resource allocation is essential. By implementing this circuit, you can ensure that multiple requesters share a resource fairly and efficiently, preventing contention and promoting equitable resource utilization.

> For specific implementation details and integration, the circuit and more details in our [Report](/round_robin.pdf).

Happy arbitrating!

## Contributors

- [Ziyad ElFayoumy](https://github.com/Zoz-HF)
- [Omar Shaban](https://github.com/omarshaban02)
- [Mahmoud Mohamed](https://github.com/Mahmoudm007)
- [Mahmoud Magdy](https://github.com/MahmoudMagdy404)
