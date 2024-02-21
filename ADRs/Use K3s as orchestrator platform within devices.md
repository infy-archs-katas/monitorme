# Use K3s as orchestrator platform within devices

## Status
ACCEPTED

## Context
Applications running on IOT devices which is used to capture patient vitals should be able to recover from unexpected failures without manual intervensions.

## Decision
The IOT devices needs to have [K3s](https://k3s.io/) installed which will be the orchestrator platform to monitor all software components running inside the device. This ***K3s*** cluster can be monitored remotely using tools like [Rancher](https://www.rancher.com/products/k3s).

## Consequences
Whenever application components crashes unexpectedly, the [K3s](https://k3s.io/) will make sure the components are restarted automatically without manual intervention. 
