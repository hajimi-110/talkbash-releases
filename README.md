# TalkBash Releases

TalkBash 安装包的发布仓库，源码在 [hajimi-110/talkbash](https://github.com/hajimi-110/talkbash)。

安装包内置单文件可执行程序，**不依赖 Python 环境**，装完直接敲 `tb` 即可使用。

## 最新版本

### v0.1.1

| 平台 | 文件 |
| --- | --- |
| 通用自解压（推荐） | `talkbash-0.1.1-linux-x86_64.run` |
| RHEL / CentOS / Rocky / AlmaLinux | `talkbash-0.1.1-1.x86_64.rpm` |
| Debian / Ubuntu | `talkbash_0.1.1-1_amd64.deb` |

从 [v0.1.1](https://github.com/hajimi-110/talkbash-releases/releases/tag/v0.1.1) 下载。

**通用自解压包**（任何 Linux 发行版都能用）：

```bash
chmod +x talkbash-0.1.1-linux-x86_64.run

./talkbash-0.1.1-linux-x86_64.run                 # 仅当前用户 → ~/.local/bin
sudo ./talkbash-0.1.1-linux-x86_64.run --system   # 所有用户 → /usr/local/bin

./talkbash-0.1.1-linux-x86_64.run --uninstall               # 卸载当前用户的安装
sudo ./talkbash-0.1.1-linux-x86_64.run --uninstall --system # 卸载全局安装
```

普通用户执行 `--system` 会自动通过 `sudo` 重新执行。支持 `--prefix DIR` 安装到自定义目录。

**RPM / DEB**：

```bash
sudo dnf install ./talkbash-0.1.1-1.x86_64.rpm
sudo apt install ./talkbash_0.1.1-1_amd64.deb
```

## 系统要求

Linux x86-64，glibc ≥ 2.17。二进制在 manylinux2014（CentOS 7）基线上构建，覆盖：

| 发行版 | glibc | 是否可用 |
| --- | --- | --- |
| CentOS / RHEL 7 | 2.17 | 可用 |
| Debian 9 / 10 / 11 / 12 / 13 | 2.24+ | 可用 |
| Ubuntu 16.04 / 18.04 / 20.04 / 22.04 / 24.04 | 2.23+ | 可用 |
| Rocky / AlmaLinux 8 / 9 / 10 | 2.28+ | 可用 |

## 安装之后

程序只读取 `~/.config/talkbash/config.toml`，装完先运行 `tb config` 配置 `provider`、
`base_url` 和 `api_key`，否则只有 `--help`、`config`、`log` 可用。

用法与安全模型见源码仓库的 [README](https://github.com/hajimi-110/talkbash#readme)。
