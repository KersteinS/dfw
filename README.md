# dfw
CLI tool accepting ufw-like commands to create firewall rules that docker will respect.

Use it the same way you'd use UFW to block docker containers from accessing or being accessed from the network. The interfaces of note are the default interface to the internet (e.g. eth0) and the docker0 interface. Note that docker-compose containers use their own interfaces not docker0, so DFW's default policies try to catch those with the default IP subnet ranges for docker containers. If you use non-default docker interfaces or IP subnet ranges, you'll need to add your own specific rules to catch that traffic.

Quirks:
1. In order for the DOCKER-USER chain to catch traffic an input or output interface must be specified for every rule. The default interface to the internet will be provisioned for rules that don't specify what interface they should be "on". 
2. Related to the above, the concept of route rules from UFW doesn't really apply in DFW, so route syntax is not supported. 
3. Comma separated port ranges are not currently supported. Support is planned in the future.
4. Application support similar to UFW's functionality is planned, but not yet implemented.
5. Although it is functional, this program is still a work-in-progress and bugs or other errors likely exist.
