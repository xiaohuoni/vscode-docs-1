---
Order: 5
Area: setup
TOCTitle: Network
ContentId: 84F36EDE-4D66-4A2E-B4D1-F020C73EB2AD
PageTitle: Setup Visual Studio Code's Network Connection
DateApproved: 3/7/2019
MetaDescription: Setup VS Code's Network Connection.
---
# Network Connections in Visual Studio Code (Visual Studio Code 中的网络连接)

Visual Studio Code is built on top of [Electron](https://electron.atom.io/) and benefits from all the networking stack capabilities of [Chromium](https://www.chromium.org/). This also means that VS Code users get much of the networking support available in [Google Chrome](https://www.google.com/chrome/index.html).

Visual Studio Code 构建在 [Electron](https://electron.atom.io/) 之上，并且得益于 [Chromium](https://www.chromium.org/) 的所有网络堆栈功能。

## Common hostnames (公用主机名)

A handful of features within VS Code require network communication to work, such as the auto-update mechanism, querying and installing extensions, and telemetry. For these features to work properly in a proxy environment, you must have the product correctly configured.

VS Code 中的一些特性需要网络通信才能工作，例如自动更新机制、查询和安装扩展以及遥测。要使这些功能在代理环境中正常工作，必须正确配置产品。

If you are behind a firewall which needs to whitelist domains used by VS Code, here's the list of hostnames you should allow communication to go through:

如果防火墙需要将 VS Code 添加到白名单才能使用的话，这里有一些允许通信通过的主机名列表：

* `update.code.visualstudio.com`
* `code.visualstudio.com`
* `go.microsoft.com`
* `vscode.blob.core.windows.net`
* `marketplace.visualstudio.com`
* `*.gallerycdn.vsassets.io`
* `rink.hockeyapp.net`
* `vscode.search.windows.net`
* `raw.githubusercontent.com`
* `vsmarketplacebadge.apphb.com`

## Proxy server support (代理服务器支持)

VS Code has exactly the same proxy server support as Google Chromium. Here's a snippet from [Chromium's documentation](https://www.chromium.org/developers/design-documents/network-settings):

VS Code 与 Google Chromium 具有完全相同的代理服务器支持。下面是 [Chromium 文档](https://www.chromium.org/developers/design-documents/network-settings)中的一个片段：

```
"The Chromium network stack uses the system network settings so that users and administrators can control the network settings of all applications easily. The network settings include:

 - proxy settings
 - SSL/TLS settings
 - certificate revocation check settings
 - certificate and private key stores"
```

This means that your proxy settings should be picked up automatically.

这意味着你能够自动获取你的代理设置。

Otherwise, you can use the following command line arguments to control your proxy settings:

否则，可以使用以下命令行参数控制代理设置：

```bash
# Disable proxy
--no-proxy-server

# Manual proxy address
--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"

# Manual PAC address
--proxy-pac-url=<pac-file-url>

# Disable proxy per host
--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]
```

[Click here](https://www.chromium.org/developers/design-documents/network-settings) to know more about these command line arguments.

[单击此处](https://www.chromium.org/developers/design-documents/network-settings)了解有关这些命令行参数的更多信息。

### Authenticated proxies (已验证的代理)

Authenticated proxies should work seamlessly within VS Code with the addition of [PR #22369](https://github.com/Microsoft/vscode/pull/22369).

经过身份验证的代理可以在 VS Code 中无缝工作，并添加 [PR #22369](https://github.com/Microsoft/vscode/pull/22369)。

The authentication methods supported are:

支持的身份验证方法有：

* Basic
* Digest
* NTLM
* Negotiate

When using VS Code behind an authenticated HTTP proxy, the following authentication popup should appear:

在经过身份验证的 HTTP 代理后面使用 VS Code 时，应出现以下身份验证弹出窗口：

![proxy](images/network/proxy.png)

Note that SOCKS5 proxy authentication support isn't implemented yet; you can follow the [issue in Chromium's issue tracker](https://bugs.chromium.org/p/chromium/issues/detail?id=256785).

请注意，SOCKS5 代理身份验证支持尚未实现；你可以在 [Chromium 的问题跟踪器](https://bugs.chromium.org/p/chromium/issues/detail?id=256785)中跟踪该问题。

[Click here](https://www.chromium.org/developers/design-documents/http-authentication) to read more about HTTP proxy authentication within VS Code.

[单击此处](https://www.chromium.org/developers/design-documents/http-authentication)阅读有关 VS Code 中 HTTP 代理身份验证的更多信息。

### SSL certificates (SSL 证书)

Often HTTPS proxies rewrite SSL certificates of the incoming requests. Chromium was designed to reject responses which are signed by certificates which it doesn't trust. If you hit any SSL trust issues, there are a few options available for you:

通常，HTTPS 代理重写传入请求的 SSL 证书。Chromium 被设计为拒绝签署不信任的证书的响应。如果遇到任何 SSL 信任问题，你可以使用以下几个选项：

* Since Chromium simply uses the OS's certificate trust infrastructure, the preferred option is to add your proxy's certificate to your OS's trust chain. [Click here](https://www.chromium.org/Home/chromium-security/root-ca-policy) to read more about the Root Certificate Policy in Chromium.
* If your proxy runs in `localhost`, you can always try the [`--allow-insecure-localhost`](https://peter.sh/experiments/chromium-command-line-switches/#allow-insecure-localhost) command line flag.
* If all else fails, you can tell VS Code to ignore all certificate errors using the [`--ignore-certificate-errors`](https://peter.sh/experiments/chromium-command-line-switches/#ignore-certificate-errors) command line flag. **Warning:** This is **dangerous** and **not recommended**, since it opens the door to security issues.

* 由于 Chromium 只使用 OS 操作系统的证书信任基础结构，所以首选的选项是将代理的证书添加到操作系统的信任链中。[单击此处](https://www.chromium.org/Home/chromium-security/root-ca-policy)阅读有关 Chromium 中根证书策略的更多信息。
* 如果代理在 `localhost` 中运行，则可以尝试 [`--allow-insecure-localhost`](https://peter.sh/experiments/chromium-command-line-switches/#allow-insecure-localhost) 命令行标志。
* 如果所有其他失败，可以使用 [`--ignore-certificate-errors`](https://peter.sh/experiments/chromium-command-line-switches/#ignore-certificate-errors) 命令行标志告诉 VS Code 忽略所有证书错误。

## Legacy proxy server support (旧代理服务器支持)

Extensions don't benefit yet from the same proxy support that VS Code supports. You can follow this issue's development in [GitHub](https://github.com/Microsoft/vscode/issues/12588).

扩展还没有从 VS Code 支持相同的代理支持中获益。你可以在 [Github](https://github.com/Microsoft/vscode/issues/12588) 中跟踪此问题的发展。

Similarly to extensions, a few other VS Code features don't yet fully support proxy networking, namely the CLI interface. The CLI interface is what you get when running `code --install-extension vscodevim.vim` from a command prompt or terminal. You can follow this issue's development in [GitHub](https://github.com/Microsoft/vscode/issues/29910).

与扩展类似，其他一些 VS Code 特性还不完全支持代理网络，即 CLI 接口。当从命令提示符或终端运行 `code --install-extension vscodevim.vim` 时，你就能得到 CLI 接口。你可以在 [Github](https://github.com/Microsoft/vscode/issues/29910) 中跟踪此问题的发展。

Due to both of these constraints, the `http.proxy`, `http.proxyStrictSSL` and `http.proxyAuthorization` variables are still part of VS Code's settings, yet they are only respected in these two scenarios.

由于这两个约束，`http.proxy`, `http.proxyStrictSSL` 和 `http.proxyAuthorization` 变量仍然是vs代码设置的一部分，但它们仅在这两个方案中受关注。

## Troubleshooting (故障排除)

Here are some helpful links that might help you troubleshoot networking issues in VS Code:

以下是一些有用的链接，可以帮助你解决 VS Code 中的网络问题：

* [Network Settings](https://www.chromium.org/developers/design-documents/network-settings)
* [Debugging problems with the network proxy](https://www.chromium.org/developers/design-documents/network-stack/debugging-net-proxy)
* [Configuring a SOCKS proxy server in Chrome](https://www.chromium.org/developers/design-documents/network-stack/socks-proxy)
* [Proxy settings and fallback (Windows)](https://www.chromium.org/developers/design-documents/network-stack/proxy-settings-fallback)

* [网络设置](https://www.chromium.org/developers/design-documents/network-settings)
* [网络代理调试问题](https://www.chromium.org/developers/design-documents/network-stack/debugging-net-proxy)
* [在 Chrome 中配置 SOCKS 代理服务器](https://www.chromium.org/developers/design-documents/network-stack/socks-proxy)
* [代理设置和回退 (Windows)](https://www.chromium.org/developers/design-documents/network-stack/proxy-settings-fallback)
