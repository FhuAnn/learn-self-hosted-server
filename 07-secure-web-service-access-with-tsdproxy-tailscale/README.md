# Tailscale Account Configuration 
# Configure my TSD-Proxy
# Using TSDProxy to config for FileBrowser
- The url that links to portainer is: https://portainer.tailscale.net. but it just is accessible from the Tailscale network.


## Why you need to find open ports
- Each service needs a unique host port.
- Examples:
  - Portainer: 9000
  - File Browser: 8080
  - TSDProxy: 8081
- As services increase, tacking used ports becomes harder.
- It's necessary to know which ports are free.

## Using ss to find open ports
- Use the ss (socket statistics) command to see ports in use ss -nult.
- Show active TCp/UDP listening ports
  -  -n: Numberic output (no hostname resolution)
  - -u: UDP sockets
  - -t: TCP sockets
  - -l: listening sockets

## How tochooose a port to use
- Match host and container ports when posible 
- If a host port is already used, incement logically
- All ports must be < = 65535 ( 880800 is invaid(above 65535))