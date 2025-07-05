# 集成 CE-插件 至PE系统
> 本节将指导您如何将 CE-插件 集成到您的PE系统中，以实现 CE-插件 的加载功能。
## CE-RAMOS 插件加载器

- 下载：[CE-插件加载器.exe](https://p0.ce-ramos.cn/CE-RAMOS%E6%96%87%E4%BB%B6/CE-%E6%8F%92%E4%BB%B6%E5%8A%A0%E8%BD%BD%E5%99%A8/CE-%E6%8F%92%E4%BB%B6%E5%8A%A0%E8%BD%BD%E5%99%A8.exe)
CE-RAMOS 插件加载器是一款图形化工具，在命令行模式下运行时不会显示通知（仅在加载开始和结束时提示）。
:::danger 警告：
若 SysWOW64 中没有 wshom.ocx 可能会影响 CE-RAMOS 插件加载器加载 CE-插件 ！
:::

> CE-RAMOS 插件加载器可配置PE名称、版本、官网，配置文件内容请参考如下内容：
>
><div class="language- vp-adaptive-theme"><button title="Copy Code" class="copy"></button><span class="lang"></span><pre class="shiki shiki-themes github-light github-dark vp-code" tabindex="0"><code><span class="line"><span>[ CE-RAMOS 插件加载器]</span></span>
><span class="line"><span>PE名称=Cloud-PE</span></span>
><span class="line"><span>PE版本=1.0</span></span>
><span class="line"><span>PE官网=https://cloud-pe.cn</span></span>
><span class="line"><strong>;此配置文件需使用UTF-8格式保存</strong></span>
><span class="line"><strong>;此配置文件需放在 CE-RAMOS插件加载器 同目录中，并命名为 [info.cfg]</strong></span>
><span class="line"><strong>;配置文件中不支持Unicode字符</strong></span></code></pre></div>

>以下为命令行参数的说明，以帮助您实现 CE-插件 的相关功能
>
>（请注意，不同版本的 CE-RAMOS 插件加载器功能可能有所变化，以下展示的功能为通用功能）
>
>:::tip 提示
>您可以通过输入一个不存在的命令行参数来调用 CE-RAMOS 插件加载器，以显示所有可用命令参数及其说明。
>:::
>```
> CE-RAMOS 插件加载器使用说明：
> CE-RAMOS 插件加载器.exe [参数]
>参数：
>  main               搜索并加载所有 CE-插件 （该选项只能使用一次，建议设置为开机默认执行）
>  <CE-插件 路径>      加载指定路径下的 CE-插件 
>```