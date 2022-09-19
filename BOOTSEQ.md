# Boot sequencing

## Entities

Entities optionally participating in the boot/reboot/shutdown processes:

- Platform UEFI/BIOS of the Server
- Platform BMC of the Server
- xPU BMC
- xPU ATF/UEFI/BIOS

## Asumptions

- Resetting the xPU is assumed to cause PCIe errors that will crash the server.
  - While this is a plausible scenario for a while, this will cause challenges for deploying an OS on the xPU and when running multi-xPU deployments. OPI should work with Linux Foundation to encourage host and OS developers to properly manage the response by the host and the xPU from a Reset
- There are use cases for network boot only.
- xPU boot can take some time (full linux distro)
- There is communication between some of the entities from above
- More...

## Bootup

- Power events
  - Server is Powered On
  - xPU receives power and starts booting
  - These events may not be synchronous. The xPU may be installed in a PICe slot providing persistent power. xPU power cycle may be a function of the host BMC (and potentially the xPU BMC) rather than the power state of the host
- What is the boot order?
  - Should Host OS wait for xPU to finish boot ?
  - Should xPU OS wait for host to finish boot ?
  - Should xPU and host be loosely coupled during boot phase?
  - who tells Host OS/xPU OS to wait and how ?
  - who tells Host OS to to continue / start booting ?
  - is Host CPU halted ?
  - can we wait in UEFI/BIOS in case of network boot via xPU ?
- Should host continue booting even if xPU failed to boot after timeout ?
- What are the implications of one xPU failing boot in a multi-xPU deployment ?
- More...

## xPU and host reboot

- Reset scenarios
  - What happens when host reboots while xPU continues execution (e.g. after host lifecycle event)
  - What happens when xPU reboots while host continues execution (e.g. after xPU lifecycle event)
- xPU OS/FW reboot assumed to cause Host OS crash
  - This will cause challenges for xPU OS deployment and multi-xPU depolyments. OPI should work with Linux Foundation to encourage host and OS developers to manage the response to a Reset on the PCIe bus
- How xPU can reboot ? 
  - Can notify Host OS that reboot is about to happen ? 
  - IRQ ? 
  - OS specific ? 
  - Through BMC?
- More...

## Graceful shutdown

- Should Host notify to xPU when reboot requested (linux shutdown/reboot command) and how ?
  - How does xPU reaction change if it is installed in a persistent power slot
- Should xPU perfoms any actions on Host reboot request ?
- When/How xPU can notify Host OS that reboot can happen/continue
  - Can xPU deny a host reboot/powercycle event?
  - Does persistent power change this behavior?
- How does host respond to a xPU going off line? (during lifecycle event etc.)
- More...

## Error handling

- what happens during Host OS crash / core dump ?
- what happens during xPU OS crash / core dump ?
- More...
