AWS Application Discovery Service helps you plan your migration to the AWS cloud by collecting usage and configuration data about your on-premises servers. 

Application Discovery Service is integrated with AWS Migration Hub, which simplifies your migration tracking. After performing discovery, you can view the discovered servers, group them into applications, and then track the migration status of each application from the Migration Hub console. 

The discovered data can be exported for analysis in Microsoft Excel or AWS analysis tools such as Amazon Athena and Amazon QuickSight.

Application Discovery Service offers two ways of performing discovery and collecting data about your on-premises servers:

 - Agentless discovery can be performed by deploying the AWS Agentless Discovery Connector (OVA file) through your VMware vCenter. After the Discovery Connector is configured, it identifies virtual machines (VMs) and hosts associated with vCenter. The Discovery Connector collects the following static configuration data: Server hostnames, IP addresses, MAC addresses, and disk resource allocations. Additionally, it collects the utilization data for each VM and computes average and peak utilization for metrics such as CPU, RAM, and Disk I/O. You can export a summary of the system performance information for all the VMs associated with a given VM host and perform a cost analysis of running them in AWS.

 - Agent-based discovery can be performed by deploying the AWS Application Discovery Agent on each of your VMs and physical servers. The agent installer is available for both Windows and Linux operating systems. It collects static configuration data, detailed time-series system-performance information, inbound and outbound network connections, and processes that are running. You can export this data to perform a detailed cost analysis and to identify network connections between servers for grouping servers as applications.


---

# AWS Application Discovery Service

Collects data about on-premises servers to plan AWS migrations.

## Discovery Methods

**Agentless Discovery (Connector)**
- VMware vCenter virtual appliance
- Collects: VM inventory, CPU/memory/disk utilization, network info
- No agent installation needed

**Agent-based Discovery**
- Install AWS Discovery Agent on servers
- Collects: System config, performance, running processes, network connections
- Works on physical and virtual servers (any hypervisor)

## Data Collected

- Server specifications (CPU, memory, disk)
- Resource utilization metrics
- Network dependencies between servers
- Running processes and applications

## Integration

- Data sent to **AWS Migration Hub**
- Can export to S3 for analysis
- Integrates with AWS Migration Hub Strategy Recommendations

## Use Cases

- Plan migration sizing (right-size EC2 instances)
- Identify application dependencies
- Group servers for migration waves
- Cost estimation for AWS resources

## Key Points

- Agent-based provides more detailed data than agentless
- Data stored for 90 days
- Can use both methods simultaneously
- Supports Windows and Linux


