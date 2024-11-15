# Kubernetes Deployment Overview

A Kubernetes Deployment manages a set of Pods to run an application workload

* Provides declarative updates for Pods and ReplicaSets
* Ensures an application remains available by gradually replaces old Pods with new ones without downtime
* Maintains application stability by allowing users to roll back to a previous version in case something goes wrong during an update
* Allows users to view and revert to previous versions by keeping track of the history of all changes made
* Ensures updates are applied gradually and safely by leveraging controlled rollouts of new versions
