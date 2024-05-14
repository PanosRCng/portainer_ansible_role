# ansible role - portainer docker stack (portainer agent / portainer server)


#### hosts.yml - inventory example
```
---

portainer:
  hosts:
    host1.example:
      portainer_server: true
    host2.example:
```

#### portainer.yml - playbook example
```
---

- name: Deploy portainer

  hosts: portainer

  gather_facts: false

  roles:
    - portainer

  vars:

    ansible_user: example_user

    docker_user: example_user

    portainer_docker_stack_directory: "/home/example_user/docker_stacks/portainer_docker_stack"

    portainer_network_subnet: "172.17.0.0/24"
    portainer_network_gateway: "172.17.0.1"

    portainer_agent_port: 9001

    portainer_server_host_port: 9000
    portainer_server_user_id: 1000
    portainer_server_group_id: 1000
    portainer_server_reset_stack: true
    portainer_server_admin_user: example_admin_user
    portainer_server_admin_password: example_admin_password
```