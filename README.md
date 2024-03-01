# Demo of HashiCorp Terraform Flexible Deployment Options (FDO)

This is still WIP.  Not fully working.

This is a demo of HashiCorp Vault's Vault Secrets Operator component which allows for syncing of secrets stored or dynamically generated from HashiCorp Vault to Kubernetes (K8s) secrets.  This has a couple of benefits.
- HashiCorp Vault automates generation of shortlived credentials to your important data stores to comply with password rotation policies
- Application Developers can still work with native K8s secrets without having to change their application code or integrate with HashiCorp Vault directly
- Performance is better than using Vault agent sidecars as the rotation of secrets is done in a single place.
- Restart of application pods is done using the native K8s mechanism when the secret is refreshed.

In this demo, we will cover:
- Setup of Vault's Dynamic Secret
- Configuration of VSO to utilize the dynamic secret
- Testing of application pods restart when secrets are refreshed
- Configure the caching persistence in VSO (optional)


You can use Visual Studio Code to run the notebook by:
- Installing "Jupyter" extension. Ref: https://www.alphr.com/vs-code-open-jupyter-notebook/
- Install the jupyter kernel for bash. Ref: https://pypi.org/project/bash_kernel/
```shell
pip install bash_kernel
python -m bash_kernel.install
```
