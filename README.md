# cmkagent

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/cmkagent) [![Testing Build](https://github.com/rolehippie/cmkagent/workflows/testing/badge.svg)](https://github.com/rolehippie/cmkagent/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/cmkagent/workflows/readme/badge.svg)](https://github.com/rolehippie/cmkagent/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/cmkagent/workflows/galaxy/badge.svg)](https://github.com/rolehippie/cmkagent/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/cmkagent)](https://github.com/rolehippie/cmkagent/blob/master/LICENSE) 

Ansible role to install an CheckMK agent and some local checks. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [cmkagent_download_url](#cmkagent_download_url)
  * [cmkagent_extra_checks](#cmkagent_extra_checks)
  * [cmkagent_extra_packages](#cmkagent_extra_packages)
  * [cmkagent_extra_plugins](#cmkagent_extra_plugins)
  * [cmkagent_general_checks](#cmkagent_general_checks)
  * [cmkagent_general_packages](#cmkagent_general_packages)
  * [cmkagent_general_plugins](#cmkagent_general_plugins)
  * [cmkagent_python_shebang](#cmkagent_python_shebang)
  * [cmkagent_python_symlink](#cmkagent_python_symlink)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### cmkagent_download_url

Base URL to download the files from

#### Default value

```YAML
cmkagent_download_url:
```

#### Example usage

```YAML
cmkagent_download_url: https://demo.checkmk.com/demo/check_mk/check_mk/agents
```

### cmkagent_extra_checks

List of extra local checks to enable

#### Default value

```YAML
cmkagent_extra_checks: []
```

### cmkagent_extra_packages

List of additional packages to install

#### Default value

```YAML
cmkagent_extra_packages: []
```

### cmkagent_extra_plugins

List of extra plugins to enable

#### Default value

```YAML
cmkagent_extra_plugins: []
```

### cmkagent_general_checks

List of local checks to enable

#### Default value

```YAML
cmkagent_general_checks:
  - name: zombie_processes
    cache_time: 300
    src: checks/zombie_processes.j2
    warn: 5
    crti: 10
    state: present
```

### cmkagent_general_packages

List of packages to install

#### Default value

```YAML
cmkagent_general_packages: []
```

### cmkagent_general_plugins

List of plugins to enable

#### Default value

```YAML
cmkagent_general_plugins:
  - name: mk_inventory
    url: https://raw.githubusercontent.com/tribe29/checkmk/master/agents/plugins/mk_inventory.linux
```

### cmkagent_python_shebang

Package to install shebang compatible python

#### Default value

```YAML
cmkagent_python_shebang: python-is-python3
```

### cmkagent_python_symlink

Symlink target for shebang compatible python

#### Default value

```YAML
cmkagent_python_symlink: /usr/bin/python3
```

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
