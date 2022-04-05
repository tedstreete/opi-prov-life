# Notes from today meeting April 5

## Docs
- please look at https://opentelemetry.io/docs/
- please look at https://github.com/silicom-ltd/uBMC
- please look at https://opencomputeproject.github.io/onie/overview/
- please look at https://fidoalliance.org/intro-to-fido-device-onboard/
- please look at https://www.rfc-editor.org/rfc/pdfrfc/rfc8572.txt.pdf (Secure Zero Touch Provisioning (SZTP))

## Priorities
- From capacity / interest / natural flow - we beleive we should start with "Initial DPU/IPU discovery and Provisioning"
- "Monitoring & Telemetry" is low hanging fuit, probably with https://opentelemetry.io so this is the second area we start working on
- Next will be "Scheduling" (Umesh and Travis votes) and "Lifecycle" (Tedd vote)
- Rest of the group supported the "Initial DPU/IPU discovery and Provisioning" or remained silent

## Monitoring & Telemetry
- We are picking a serious exploration of adopting https://opentelemetry.io/ for OPI
- OpenTemetry suports those data sources: Traces, Metrics, Logs
- OpenTemetry is made up of several main components: Specification, SDK, Collector
- OpenTemetry collector supports several deployments: side-car container in the pod, node, cluster, chaining and others...

## Initial DPU/IPU discovery and Provisioning
- We have to start working on requirements
- Let's deep dive in Fido, Sztp, Onie and others
- Inband vs OOB provisioning
- Soft-BMC concept on arm cores when DOPU comes without BMC
- External Provisioning entity/server (PXE, DHCP, TFTP, HTTP, Randevious, ...)
- Without External Provisioning entity/server (Edge deployment, IoT-like)

## Action items:
- Kyle: please start IPDK doscussion on OpenTelemetry
- Gene: please dive into FDO and SZTP a bit more and come back present to us
- Gene: please present how provisioning works today in Verizon
- Elad: please present how provisioning works today in your environment
- Andy+Lee: please present how provisioning works today in Dell
