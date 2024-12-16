# Settings

The Settings view enables you to view and modify the Docker daemon configurations, as well as stop, start, or restart the Docker daemon.

For common configurations, 1Panel offers a visual configuration form:

- Registry mirrors: When application installation fails or image pulling times out, you can try to configure the image registry mirrors.
- Insecure registries: For adding repositories that use the HTTP protocol, you can do so here.
- IPv6: Enables or disables the IPv6 feature, which requires the creation of an IPv6 container network before it can be enabled.
- Log option: Configure the maximum size and number of container log files
- iptables: Enables or disables automatic configuration of iptables rules for Docker.
- Live restore: Determines whether to stop all containers when the Docker daemon service is stopped.
- cgroup driver
- Unix domain socket

In addition, you can use text mode to view and modify all configurations.
