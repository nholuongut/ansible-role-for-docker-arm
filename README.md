# Ansible Role: Docker for ARM

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

An Ansible Role that installs [Docker](https://www.docker.com) on Linux, specially tailored for ARM-based computers like the Raspberry Pi.

If you need a more flexible and generic role for Docker on non-ARM platforms like x86, please check out [`nholuong.docker`](https://galaxy.ansible.com/nholuong/docker).

## Role Usage in Real-world projects

Besides the documentation here, please see the [Raspberry Pi Dramble](http://www.pidramble.com) for an example of this role in action, being used with multiple Raspberry Pis to build a Kubernetes cluster, or [Drupal Pi](https://github.com/nholuong/drupal-pi) for an example of use with a single Raspberry Pi.

## Requirements

If installing Docker Compose, requires Python Pip already be installed (you can use `nholuong.pip` to install it).

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    docker_version: latest

The version of Docker to install. You can specify an exact version to lock it in (check for available versions with `apt-cache madison docker-ce`).

    docker_install_recommends: false

Whether to install recommended packages alongside docker-ce.

    docker_install_compose: true

Whether to install Docker Compose via Pip.

    docker_users:
      - user1
      - user2

A list of system users to be added to the `docker` group (so they can use Docker on the server).

    docker_pip_executable: pip3

Set this to `pip` for Python 2 or `pip3` for Python 3.

## Use with Ansible (and `docker` Python library)

Many users of this role wish to also use Ansible to then _build_ Docker images and manage Docker containers on the server where Docker is installed. In this case, you can easily add in the `docker` Python library using the `nholuong.pip` role:

```yaml
- hosts: rpi

  vars:
    pip_package: python3-pip
    pip_install_packages:
      - name: docker

  roles:
    - nholuong.pip
    - nholuong.docker_arm
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: rpi

  vars:
    pip_package: python3-pip

  roles:
    - nholuong.pip
    - nholuong.docker_arm
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
