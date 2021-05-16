# Changelog

## [2.0.0](https://github.com/extra2000/grafana-box/compare/v1.0.0...v2.0.0) (2021-05-16)


### ⚠ BREAKING CHANGES

* **nginx-formula:** nginx pod need to be fresh deployed
* **grafana-formula:** require `extra2000/nginx-fornula v3.x` and pillar file `pillar/grafana.sls.example` has non-backward compatibility changes.
* **podman:** Podman pillar file `salt/roots/pillar/podman.sls` has been removed.
* **podman-formula:** Podman formula has major changes

### Features

* **grafana-formula:** upgrade to `v3.0.0` ([78dec2e](https://github.com/extra2000/grafana-box/commit/78dec2e0c21fa5afc42146060250935775509496))
* **nginx-formula:** upgrade to `v3.0.1` ([09bbeb6](https://github.com/extra2000/grafana-box/commit/09bbeb6c1fb4a5cdb25af3e7c858c9102170646e))
* **podman:** Add `salt/roots/pillar/podman.sls.example` ([2cb852e](https://github.com/extra2000/grafana-box/commit/2cb852ede058602df665988796d55fbc628f94d7))
* **podman-formula:** Upgrade from `v2.2.2` to `v4.0.0` ([b7d9f4e](https://github.com/extra2000/grafana-box/commit/b7d9f4e4dd31b63713547ab2454b702b58e393b5))


### Code Refactoring

* **podman:** Remove Podman formula pillar file `salt/roots/pillar/podman.sls` ([bce9159](https://github.com/extra2000/grafana-box/commit/bce91592bbea7d9f4c5e61dd16177c1a72f75a9e))


### Documentations

* **README:** Add instructions to create `salt/roots/pillar/podman.sls` ([38f059b](https://github.com/extra2000/grafana-box/commit/38f059b733bb744c9b11e50ff24e492c0b45df2f))
* **README:** Remove `systemctl --user daemon-reload` ([c841974](https://github.com/extra2000/grafana-box/commit/c84197453c0230fa997403bd7dfad4c2bdbad772))


### Fixes

* **pillar/grafana.sls.example, pillar/nginx.sls.example:** Fix Podman networking conflicts ([7a6874e](https://github.com/extra2000/grafana-box/commit/7a6874eb24191a46e7272c93cb013c32736c4521))


### Continuous Integrations

* **AppVeyor:** Add instructions to create `salt/roots/pillar/podman.sls` ([30a0355](https://github.com/extra2000/grafana-box/commit/30a03558ac3efbc72a5450fbd43da3041e92ba77))
* **AppVeyor:** remove old nginx-formula workaround ([d4ec277](https://github.com/extra2000/grafana-box/commit/d4ec277290a4e63be3be21ba5f11497e3ed60850))

## 1.0.0 (2021-04-30)


### Features

* **salt:** Add implementations for states in `salt/` ([7746140](https://github.com/extra2000/grafana-box/commit/7746140e67bb4fe4d780fc4658767d943921daac))
* **submodules:** Add [extra2000/grafana-formula v1.0.0](https://github.com/extra2000/grafana-formula/releases/tag/v1.0.0) ([0edcdc5](https://github.com/extra2000/grafana-box/commit/0edcdc5cb17ef09b11b3ac1cc3470fa72c41fbcc))
* **submodules:** Add [extra2000/nginx-formula v2.0.0](https://github.com/extra2000/nginx-formula/releases/tag/v2.0.0) ([30167f2](https://github.com/extra2000/grafana-box/commit/30167f2cabda68e66eaee9a9fb49fabe5588882d))
* **submodules:** Add [extra2000/podman-formula v2.2.2](https://github.com/extra2000/podman-formula/releases/tag/v2.2.2) ([a1593af](https://github.com/extra2000/grafana-box/commit/a1593af7992f05833f8dede12b16e06d713758c2))
* **vagrant:** Import Vagrant files from [extra2000/generic-box v1.8.0](https://github.com/extra2000/generic-box/releases/tag/v1.8.0) ([7359eb6](https://github.com/extra2000/grafana-box/commit/7359eb6e1b6d0d547182228ec0acec1d3e32cebe))


### Continuous Integrations

* Add AppVeyor with `semantic-release` bot ([3ccd75b](https://github.com/extra2000/grafana-box/commit/3ccd75be4f2e80a4025966ca659e9f3d759a31b0))


### Documentations

* **README:** Update `README.md` ([3537da4](https://github.com/extra2000/grafana-box/commit/3537da4471310a6d0644e47dbcf42972ab7611fb))
