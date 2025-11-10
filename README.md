# cmkagent

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/cmkagent)
[![General Workflow](https://github.com/rolehippie/cmkagent/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/cmkagent/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/cmkagent/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/cmkagent/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/cmkagent/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/cmkagent/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/cmkagent)](https://github.com/rolehippie/cmkagent/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.cmkagent-blue)](https://galaxy.ansible.com/rolehippie/cmkagent)

Ansible role to install an CheckMK agent and some local checks.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of contents

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [cmkagent_download_binaries](#cmkagent_download_binaries)
  - [cmkagent_download_url](#cmkagent_download_url)
  - [cmkagent_extra_checks](#cmkagent_extra_checks)
  - [cmkagent_extra_packages](#cmkagent_extra_packages)
  - [cmkagent_extra_plugins](#cmkagent_extra_plugins)
  - [cmkagent_general_checks](#cmkagent_general_checks)
  - [cmkagent_general_packages](#cmkagent_general_packages)
  - [cmkagent_general_plugins](#cmkagent_general_plugins)
  - [cmkagent_python_shebang](#cmkagent_python_shebang)
  - [cmkagent_python_symlink](#cmkagent_python_symlink)
  - [cmkagent_version](#cmkagent_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### cmkagent_download_binaries

List of binaries to download

#### Default value

```YAML
cmkagent_download_binaries:
  - check_mk_agent.linux
  - check_mk_caching_agent.linux
  - mk-job
  - waitmax
```

### cmkagent_download_url

Base URL to download the files from

#### Default value

```YAML
cmkagent_download_url: https://raw.githubusercontent.com/Checkmk/checkmk/v{{ 
  cmkagent_version }}/agents
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
    url: https://raw.githubusercontent.com/tribe29/checkmk/v{{ cmkagent_version 
      }}/agents/plugins/mk_inventory.linux
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

### cmkagent_version

Version used to download agent and plugins

#### Default value

```YAML
cmkagent_version: 2.4.0
```

## Discovered Tags

**_cmkagent_**

## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
