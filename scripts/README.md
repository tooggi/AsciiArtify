# kubeplugin: Kubectl Resource Consumption Plugin

This script allows you to check resource consumption (CPU and memory) for Kubernetes resources using `kubectl`.

## Usage

```sh
./kubeplugin [resource_type] [namespace]
```
- `resource_type`: The type of resource to check (e.g., `pods`, `nodes`). Default is `pods`.
- `namespace`: The Kubernetes namespace. Default is `default`.

Example:
```sh
./kubeplugin pods kube-system
```

## Make it a kubectl plugin

To use this script as a `kubectl` plugin (e.g., `kubectl ctop`):
1. Rename the script to `kubectl-ctop` and copy it to a directory included in your `PATH`:
   ```sh
   cp kubeplugin /usr/local/bin/kubectl-ctop
   chmod +x /usr/local/bin/kubectl-ctop
   ```

2. Now you can run:
   ```sh
   kubectl ctop [resource_type] [namespace]
   ```

