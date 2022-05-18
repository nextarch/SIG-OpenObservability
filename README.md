# SIG: Open Observability

## Introduction

With the rapid scaling of cloud native computing, the probability of system/application fault is dramatically increasing. Consequently, troubleshooting becomes more difficult and complicated. SIG-OpenObservability aims to make troubleshooting as efficient and painless as possible, either from the perspective of tackling issues or tracing performance. The eBPF-based SIG-OpenObservability will be used extensively to drive a wide variety of use cases, e.g., extracting fine-grained key observability data at low overhead from linux kernel subsystems (MM, CPU, Net, Block IO, etc.), helping application developers trace applications, providing insights for performance troubleshooting, and much more.

## Scenarios

#### Observability & Monitoring

Instead of relying on static counters and gauges exposed by the operating system, eBPF enables the collection & in-kernel aggregation of custom metrics and generation of visibility events based on a wide range of possible sources. This extends the depth of visibility that can be achieved as well as reduces the overall system overhead significantly by only collecting the visibility data required and by generating histograms and similar data structures at the source of the event instead of relying on the export of samples.

#### Tracing & Profiling

The ability to attach eBPF programs to trace points as well as kernel and user application probe points allows unprecedented visibility into the runtime behavior of applications and the system itself. By giving introspection abilities to both the application and system side, both views can be combined, allowing powerful and unique insights to troubleshoot system performance problems. Advanced statistical data structures allow to extract meaningful visibility data in an efficient manner, without requiring the export of vast amounts of sampling data as typically done by similar systems.


#### Security

Building on the foundation of seeing and understanding all system calls and combining that with a packet and socket-level view of all networking operations allows for revolutionary new approaches to securing systems. While aspects of system call filtering, network-level filtering, and process context tracing have typically been handled by completely independent systems, eBPF allows for combining the visibility and control of all aspects to create security systems operating on more context with better level of control.

#### Networking

The combination of programmability and efficiency makes eBPF a natural fit for all packet processing requirements of networking solutions. The programmability of eBPF enables adding additional protocol parsers and easily program any forwarding logic to meet changing requirements without ever leaving the packet processing context of the Linux kernel. The efficiency provided by the JIT compiler provides execution performance close to that of natively compiled in-kernel code.


## Ecosystem

#### Tech Lead

**Tonghao Zhang** @DiDi Global, Linux Kernel, Open vSwitch and DPDK Contributor. Interested Areas: eBPF observability, programmable networks, ultra-low-latency networking, cloud computing, edge computing, network functions virtualization, software-defined networking.

#### SIG Members

***1-2 member per organization***

| Name                        | Organization         |
| --------------------------- | -------------------- |
| Tonghao Zhang                | DiDi Global   |
| Feng Wu                | DiDi Global   |


#### Open Source

**HuaTuo @DiDi Global** is event driven, i.e., it extracts observability data when linux kernel events that we take care of, occurs. With this data, it is easy to figure out what the root cause of issues. More importantly, **HuaTuo** can trace linux kernel/applications for performance troubleshooting because we can also sample the data, then generate a CPU flame graph effectively.
