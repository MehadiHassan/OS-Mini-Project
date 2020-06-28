# OS-Mini-Project

// Implement Bankers Algorithm 
// n--> Number of process in the system
// m--> Number of resource types

//Available:-
// 1. It is a 1-D array of size m indicating the number of available resources of each type.
// 2. Available[j]=k means , tehre are k instances of resource type Rj

//Max :
// 1. It is a 2-d array of size ‘n*m’ that defines the maximum demand of each process in a system.
// 2. Max[ i, j ] = k means process Pi may request at most ‘k’ instances of resource type Rj.

//Allocation :
// 1. It is a 2-d array of size ‘n*m’ that defines the number of resources of each type currently allocated to each process.
// 2. Allocation[ i, j ] = k means process Pi is currently allocated ‘k’ instances of resource type Rj

//Need :
// 1. It is a 2-d array of size ‘n*m’ that indicates the remaining resource need of each process.

// 2. Need [ i,   j ] = k means process Pi currently need ‘k’ instances of resource type Rj for its execution.

// 3. Need [ i,   j ] = Max [ i,   j ] – Allocation [ i,   j ]

//Allocationi specifies the resources currently allocated to process Pi and Needi specifies the additional resources that process Pi may still request to complete its task.

//Banker’s algorithm consists of Safety algorithm and Resource request algorithm

//Safety Algorithm

//The algorithm for finding out whether or not a system is in a safe state can be described as follows:

// 1) Let Work and Finish be vectors of length ‘m’ and ‘n’ respectively.

// Initialize: Work = Available

// Finish[i] = false; for i=1, 2, 3, 4….n


// 2) Find an i such that both

// a) Finish[i] = false

// b) Needi <= Work

// if no such i exists goto step (4)


// 3) Work = Work + Allocation[i]

// Finish[i] = true

// goto step (2)

// 4) if Finish [i] = true for all i  then the system is in a safe state

// Resource-Request Algorithm

// Let Requesti be the request array for process Pi. Requesti [j] = k means process Pi wants k instances of resource type Rj. When a request for resources is made by process Pi, the following actions are taken:

// 1) If Requesti <= Needi

// Goto step (2) ; otherwise, raise an error condition, since the process has exceeded its maximum claim.

// 2) If Requesti <= Available

// Goto step (3); otherwise, Pi must wait, since the resources are not available.

// 3) Have the system pretend to have allocated the requested resources to process Pi by modifying the state as
// follows:

// Available = Available – Requesti

// Allocationi = Allocationi + Requesti

// Needi = Needi– Requesti
