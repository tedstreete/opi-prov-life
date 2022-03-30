# Notes from today meeting March 29

## Docs
- please look at https://opentelemetry.io/docs/ we will discuss it next week
- please look at https://github.com/silicom-ltd/uBMC we will discuss it next week
- good tool for drawings that githuib works well suggested by Kyle http://draw.io

## Monitoring & Telemetry
- we want to create high level diagram (Ted will create draft PR) for
- micro-aggregator inside each DPU/IPU
- macro-aggregator between DPUs
- macro-aggregator can run on the host with DPU/IPU or on a separate host
- we want to define what telemetries are mandatory for each vendor to implement and which are optional
- we want to pick 1 standard protocol all vendors can implement (both linux and non-linux based)
- we want IPDK to implement example telemetry streaming (i.e. Telegraf + InfluxDB + Grafana) Boris will post on IPDK slack
- HW monitoring vs SW monitoring
- How we handle BMC of the DPU/IPU ? redfish relationship ?

## Initial DPU/IPU discovery
- we want to discover hundreds on DPUs/IPUs on the network first
- we must support both IPv6 and IPv4
- we want to use existing network discovery mechanisms
- homework - what is the difference/preference LLDP/SSDP/mDNS/...
- Elad suggested to use "call home" inside the network