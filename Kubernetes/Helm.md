# Helm Overview

Helm is a tool for managing Kubernetes packages (Charts)

* Helps manage Kubernetes applications
* Can create charts from scratch
* Can package charts into chart archive files (tgz)
* Can install and uninstall charts into an existing Kubernetes cluster
* Can manage the release cycle of charts that have been installed with Helm

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Helm Charts

A chart is a bundle of information necessary to create an instance of a Kubernetes application

* Help you define, install, and upgrade even the most complex Kubernetes application
* Easy to create, version, share, and publish

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Config

The config contains configuration information that can be merged into a packaged chart to create a releasable object

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Release

A release is a running instance of a chart, combined with a specific config

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Helm Client

The Helm Client is a command-line client for end users

* Responsible for local chart development, managing repositories, managing releases, etc.
* Interfaces with the Helm library (Sending charts to be installed, Requesting upgrading or uninstalling of existing releases, etc.)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Helm Library

The Helm Library provides the logic for all existing Helm operations

* Interfaces with the Kubernetes API server
* Combines a chart and configuration to build a release
* Installs charts into Kubernetes and provides the subsequent release object
* Upgrades and uninstalls charts by interacting with Kubernetes
* The standalone Helm library encapsulates the Helm logic so that it can be leveraged by different clients
* Uses REST+JSON and stores information in Secrets located inside of Kubernetes (It doesn't need its own database)
