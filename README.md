<h1 align="center">
  <a href="https://github.com/tomcdj71/public-tracker-blocker">
    <!-- Please provide path to your logo here -->
  </a>
</h1>

<div align="center">
  Public Tracker Blocker
  <br />
  <a href="https://github.com/tomcdj71/public-tracker-blocker/issues/new?assignees=&labels=bug&template=01_BUG_REPORT.md&title=bug%3A+">Report a Bug</a>
   · 
  <a href="https://github.com/tomcdj71/public-tracker-blocker/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
   · <a href="https://github.com/tomcdj71/public-tracker-blocker/discussions">Ask a Question</a>
</div>

<div align="center">
<br />


|  | |
|---|---|
| **CI/CD** | [![Main](https://github.com/tomcdj71-openclassrooms/todolist/actions/workflows/update_example/badge.svg)](https://github.com/tomcdj71-openclassrooms/todolist/actions/workflows/update_example.yaml)  |
| **Community** | [![Pull Requests welcome](https://img.shields.io/badge/PRs-welcome-ff69b4.svg?style=flat-square)](https://github.com/tomcdj71/public-tracker-blocker/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)  |
| **Open&#160;Source** | [![BSD 3-clause](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://github.com/tomcdj71/public-tracker-blocker/blob/main/LICENSE) |
| **Maintener** | [![code with love by tomcdj71](https://img.shields.io/badge/%3C%2F%3E%20with%20%E2%99%A5%20by-tomcdj71-ff1414.svg?style=flat-square)](https://github.com/tomcdj71) |
| **Tools** | [![better commits is enabled](https://img.shields.io/badge/better--commits-enabled?style=for-the-badge&logo=git&color=a6e3a1&logoColor=D9E0EE&labelColor=302D41)](https://github.com/Everduin94/better-commits) |

</div>

<details open="open">
<summary>Table of Contents</summary>

- [About](#about)
- [Built With](#built-with)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Standard usage](#standard-usage)
  - [Standalone usage](#standalone-usage)
  - [Custom list](#custom-list)
- [Support](#support)
- [Project assistance](#project-assistance)
- [Contributing](#contributing)
- [Authors & contributors](#authors--contributors)
- [License](#license)

</details>

---

## About

<table><tr><td>

> **NOTE**
> Public Tracker Blocker is a simple script that parse url lists to add to the hosts file. It helps to block public trackers so you can't use them in your torrent clients

</td></tr></table>

### Built With

> **[?]**
> Bash

## Getting Started

### Prerequisites

> **[?]**
> What are the project requirements/dependencies?

- [bash] (5.3)
- [curl]
- [awk]
- [git]

[bash]: https://tracker.debian.org/pkg/bash
[curl]: https://tracker.debian.org/pkg/curl
[awk]: https://packages.debian.org/fr/bullseye/awk
[git]: https://tracker.debian.org/pkg/git
### Installation

> **NOTE**
> **How to install this script?**
> 
> If you don't want to install this script, you can use the [hosts.example](./hosts.example) file provided.

```bash
sudo -i
cd /opt
git clone https://github.com/tomcdj71/public-tracker-blocker
cd public-tracker-blocker
chmod +x public-tracker-blocker.sh
ln public-tracker-blocker.sh /usr/local/bin/public-tracker-blocker
```

## Usage

### Standard usage
> **[?]**
> How does one go about using it?

The usage is pretty simple, you only need to use this command :
```bash
public-tracker-blocker
```


> **NOTE**
> Some options are available, discover them with `public-tracker-blocker --help`
```console
$ public-tracker-blocker --help

Usage: /usr/local/bin/public-tracker-blocker [--reload] [--update] [--help]
Options:
  --reload              Reload network after updating hosts file
  --update              Update script to latest version
  --help                Print this help message
```


### Standalone usage

> **NOTE**
> For a standalone use, you can simply append the content of the provided hosts.example into your existing /etc/hosts file : 

```bash
awk 'NR==1{print "# DO NOT DELETE THIS LINE"} NR!=1' /etc/hosts > /tmp/hosts.tmp
curl -s https://raw.githubusercontent.com/tomcdj71/public-tracker-blocker/main/hosts.example >> /tmp/hosts.tmp
sudo mv /tmp/hosts.tmp /etc/hosts
```

> **IMPORTANT**
> As this is standalone use, you could want to update from time to time.
> To do this, you can run the following :
```bash
awk '/# DO NOT DELETE THIS LINE/{exit} {print}' /etc/hosts > /tmp/hosts.tmp
grep -qxF '# DO NOT DELETE THIS LINE' /tmp/hosts.tmp || echo '# DO NOT DELETE THIS LINE' >> /tmp/hosts.tmp
curl -s https://raw.githubusercontent.com/tomcdj71/public-tracker-blocker/main/hosts.example >> /tmp/hosts.tmp
sudo mv /tmp/hosts.tmp /etc/hosts
```

### Custom list
> **NOTE**
> You can also add custom list to enhance the use of the script.

First, create a `custom-list.txt`. This file is up to you, but consider saving the list by creating a Pull Request so all the community can use it.

Once the list is created, start adding the links.

On the next run, your custom lists will be fetched.

> **Warning**
> For now, only lists from github or pastebin are supported.
> Feel free to open a Pull Request to add more supported websites.

## Support

> **[?]**
> Additional ways to contact me.

| Documentation              | Status                                                         |
| -------------------------- | -------------------------------------------------------------- |
| :bug: **Issues Board** | [open issues](https://github.com/tomcdj71/public-tracker-blocker/issues) |

## Project assistance

If you want to say **thank you** or/and support active development of Public Tracker Blocker:

- Add a [GitHub Star](https://github.com/tomcdj71/public-tracker-blocker) to the project.
- Tweet about the Public Tracker Blocker.

Together, we can make Public Tracker Blocker **better**!

## Contributing

First off, thanks for taking the time to contribute! Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make will benefit everybody else and are **greatly appreciated**.

## Authors & contributors

Thanks to [@ngosang's list](https://github.com/ngosang/trackerslist). His project made me this idea to create a script to automate this process.

## License

This project is licensed under the **BSD license**.

See [LICENSE](LICENSE) for more information.
