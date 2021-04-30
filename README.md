# grafana-box

| License | Versioning | Build |
| ------- | ---------- | ----- |
| [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) | [![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release) | [![Build status](https://ci.appveyor.com/api/projects/status/c4ichqgly48r7nt4/branch/master?svg=true)](https://ci.appveyor.com/project/nikAizuddin/grafana-box/branch/master) |

Developer box [Grafana](https://grafana.com/).


## Creating Vagrant Box

Copy example pillar files. Optionally you may want to edit the values in these files:
```
$ cp -v salt/roots/pillar/nginx.sls.example salt/roots/pillar/nginx.sls
$ cp -v salt/roots/pillar/grafana.sls.example salt/roots/pillar/grafana.sls
```

Copy vagrant file from `vagrant/examples/` and then create the vagrant box (you can change to `--provider=virtualbox` if you want to use Oracle VirtualBox provider):
```
$ cp -v vagrant/examples/Vagrantfile.grafana-box.fedora-34.x86_64.example vagrant/Vagrantfile.grafana-box
$ vagrant up --provider=libvirt
```

Provision the vagrant box:
```
$ vagrant ssh grafana-box -- sudo salt-call state.highstate
```

Deploy Grafana including MySQL and Redis:
```
$ vagrant ssh grafana-box -- sudo salt-call state.sls grafana
```

Deploy NGINX:
```
$ vagrant ssh grafana-box -- sudo salt-call state.sls grafana.config.nginx
$ vagrant ssh grafana-box -- sudo salt-call state.sls nginx.service
```


## Create systemd units for auto startup on boot

Generate systemd unit for Redis and enable it:
```
$ cd ~/.config/systemd/user
$ podman generate systemd --files --name redis-pod
$ systemctl --user daemon-reload
$ systemctl --user enable pod-redis-pod.service container-redis-pod-redis01.service
```

Generate systemd unit for MySQL and enable it:
```
$ cd ~/.config/systemd/user
$ podman generate systemd --files --name mysql-pod
$ systemctl --user daemon-reload
$ systemctl --user enable pod-mysql-pod.service container-mysql-pod-mysql01.service
```

Generate systemd unit for NGINX and enable it:
```
$ cd ~/.config/systemd/user
$ podman generate systemd --files --name nginx-pod
$ systemctl --user daemon-reload
$ systemctl --user enable pod-nginx-pod.service container-nginx-pod-srv01.service
```

Generate systemd unit for Grafana and enable it:
```
$ cd ~/.config/systemd/user
$ podman generate systemd --files --name grafana-pod
$ systemctl --user daemon-reload
$ systemctl --user enable pod-grafana-pod.service container-grafana-pod-grafana01.service
```


## Initializing Grafana

First-time login:
* username: `admin`
* password: `admin`
