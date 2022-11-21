# Linode Ansible Ceph

Ansible colection to deploy Ceph on Linode using Linode and Block Storage.

:warning: **REPO isn't finished**

## Usage

In order to run this playbook, you must create a Linode [Personal Access Token](https://www.linode.com/docs/guides/getting-started-with-the-linode-api/#get-an-access-token).

While in the in the root directory, run the following:

```bash
export LINODE_TOKEN=mytoken
ansible-playbook deploy.yml
```

This will execute the playbook, including provisioning the necessary infrastructure and configuring each new node.

## File Structure

- `config.yml` - Stores various configuration for this playbook.
- `deploy.yml` - The primary playbook file for this example.
- `roles`
  - `infra`
    - `tasks`
      - `main.yml` - The entrypoint for this role.
      - `instances.yml` - Provisions the Linode instances for this deployment.
      - `volume.yml` - Provisions a Linode volume to be attached to the instances.
  - `installation`
    - `tasks`
      - `main.yml` - The entrypoint for this role.
      - `mount_volume.yml` - Mounts and formats the attached volume.

## TODO

- [x] Infrastructure deployment
- [ ] Connect with Ceph Ansible
- [ ] Proper config