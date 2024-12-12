# Networks

The Networks view lets you manage Docker networks without having to use the CLI.

## Create a network

By clicking the `Create` button, you can create a Docker network through the creation form.

!!! info "Supported network drivers"
    - bridge: The default network driver.
    - ipvlan: IPvlan networks provide full control over both IPv4 and IPv6 addressing.
    - macvlan: Assign a MAC address to a container.
    - overlay: Overlay networks connect multiple Docker daemons together.

## Remove networks

You can directly delete specific networks from the network list, or click the `Prune` button to clean up all unused networks.

!!! tips "Tips"
    The following four networks —— none, host, bridge, and 1panel-network —— are system-provided and should not be removed.

## Additional resources

- [Docker Network Documentation](https://docs.docker.com/network)
