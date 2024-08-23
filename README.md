# CPU Scheduling Algorithms

An implementation of various CPU scheduling algorithms in C++, including FCFS, Round Robin (RR), SPN, SRT, HRRN, Feedback (FB), and Aging.

## Algorithms

### First Come First Serve (FCFS)
- **FCFS** executes processes in the order they arrive. It is simple but can lead to inefficiencies if long processes block shorter ones.

### Round Robin with Varying Time Quantum (RR)
- **RR** allocates CPU time to processes in a rotating order, using a time slice. The time quantum can vary, helping balance short and long processes.

### Shortest Process Next (SPN)
- **SPN** selects the process with the shortest burst time. This non-preemptive algorithm reduces average waiting time but can cause longer processes to wait indefinitely.

### Shortest Remaining Time (SRT)
- **SRT** is the preemptive version of SPN. It dynamically selects the process with the shortest remaining time, adapting to changes as processes arrive.

### Highest Response Ratio Next (HRRN)
- **HRRN** prioritizes processes with the highest response ratio, considering both waiting time and burst time, helping to reduce average waiting time.

### Feedback (FB)
- **FB** uses multiple priority queues, where processes are promoted or demoted based on their execution history, balancing fairness and efficiency.

### Feedback with Varying Time Quantum (FBV)
- **FBV** extends FB by assigning different time quanta to each priority level, optimizing CPU utilization.

### Aging
- **Aging** prevents starvation by gradually increasing the priority of waiting processes, ensuring all get CPU time eventually.

## Installation
1- Clone the repository

2- Install g++ compiler and make
```bash
sudo apt-get install g++ make
```
3- Compile the code using `make` command

4- Run the executable file

## Input Format
- Line 1: "trace" or "stats"
- Line 2: a comma-separated list telling which CPU scheduling policies to be analyzed/visualized along with
their parameters, if applicable. Each algorithm is represented by a number as listed in the
introduction section and as shown in the attached testcases.
Round Robin and Aging have a parameter specifying the quantum q to be used. Therefore, a policy
entered as 2-4 means Round Robin with q=4. Also, policy 8-1 means Aging with q=1.
 1. FCFS (First Come First Serve)
 2. RR (Round Robin)
 3. SPN (Shortest Process Next)
 4. SRT (Shortest Remaining Time)
 5. HRRN (Highest Response Ratio Next)
 6. FB-1, (Feedback where all queues have q=1)
 7. FB-2i, (Feedback where q= 2i)
 8. Aging
- Line 3: An integer specifying the last instant to be used in your simulation and to be shown on the timeline.
- Line 4: An integer specifying the number of processes to be simulated.
- Line 5: Start of description of processes. Each process is to be described on a separate line. For algorithms 1 through 7, each process is described using a comma-separated list specifying:

    1- String specifying a process name\
    2- Arrival Time\
    3- Service Time

- **Note:** For Aging algorithm (algorithm 8), each process is described using a comma-separated list specifying:

    1- String specifying a process name\
    2- Arrival Time\
    3- Priority
- Processes are assumed to be sorted based on the arrival time. If two processes have the same arrival time, then the one with the lower priority is assumed to arrive first.
