# OpenEdgeRobotics-nova


## private cloud compute core for Open Edge Robotics
---
### Nova Services and Components

#### nova-api service
Accepts and responds to compute API requests from end users. This service supports APIs such as the OpenStack Compute API and Amazon EC2 API, allowing administrators to perform management tasks. It is responsible for executing and managing instances.

#### nova-api-metadata service
Handles metadata requests for instances. It is used when running in multi-host mode with nova-network installed.

#### nova-compute service
A daemon responsible for creating and terminating VM instances via hypervisor APIs. Supported hypervisors include XenServer, KVM, VMWare, and others.

#### nova-scheduler service
Retrieves VM instance requests from the queue and determines the compute server node where the virtual machine will run.

#### nova-conductor module
Manages interactions between the nova-compute service and the database.

#### nova-cert module
Provides nova certificate services for X.509 certification. This is only required for the EC2 API.

#### nova-network worker daemon
Similar to nova-compute service, it handles network operations from the queue and manages network configurations.

#### nova-consoleauth daemon
Authorizes tokens for users provided by the Console Proxy. Works in conjunction with nova-novncproxy and nova-xvpvncproxy.

#### nova-novncproxy daemon
Acts as a proxy to access running instances via VNC connections, supporting browser-based noVNC clients.

#### nova-xvpvnproxy daemon
Provides a proxy for accessing running instances via VNC connections, supporting OpenStack-related Java clients.

#### nova-spiceshtml5proxy daemon
Acts as a proxy for accessing running instances via SPICE connections, supporting browser-based HTML5 clients.

#### euca2ools client
A CLI API for managing cloud resources. While not an OpenStack module, nova-api can be configured to support EC2 interfaces.

#### nova client
A command-line tool that allows users, tenant administrators, or end users to issue commands.
