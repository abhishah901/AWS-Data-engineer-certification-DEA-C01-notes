Amazon Redshift has two types of nodes: leader nodes and compute nodes.

Compute Nodes: These nodes store and process the data. They perform the heavy lifting of running queries, filtering data, and performing computations.

Leader Node: This node manages the compute nodes, receives queries, and distributes the workload across the compute nodes. It also manages external communication and aggregates the results from the compute nodes. Certain functions, including current_schema(), are leader node–only functions, meaning they can only be executed on the leader node.