# Godzilla-Suo5MemShell

Godzilla 插件: 一键注入 Suo5 内存马

目前支持的中间件和内存马类型

- Tomcat Filter
- Tomcat Servlet
- WebLogic Filter
- Jetty Filter
- Resin Filter
- JBoss/WildFly Filter

具体版本的兼容性参考 GodzillaMemoryShellProject

```
Tomcat 5 - 10
Jetty 7 - 11.0.11
JBoss (WildFly) 8 - 27.0.0
Resin 3 - 4.0.66
WebLogic 10.3.6 - 14
```

参考:

[https://github.com/zema1/suo5](https://github.com/zema1/suo5)

[https://github.com/BeichenDream/Godzilla](https://github.com/BeichenDream/Godzilla)

[https://github.com/BeichenDream/GodzillaMemoryShellProject](https://github.com/BeichenDream/GodzillaMemoryShellProject)

注意 Releases 中的 jar 不一定是最新的, 建议按照下面的说明自行手动编译

## Usage

内存马注入部分参考了 Godzilla 内置的 FilterShell 和 MemoryShell 插件

![img8.png](img/img8.png)

![img14.png](img/img14.png)

### 注入 Tomcat Filter 内存马

需要指定 urlPattern, 一般不建议设置为 `/*`

filterName 为可选项, 如果为空则使用 Godzilla 默认生成的随机名称

![img9.png](img/img9.png)


![img10.png](img/img10.png)

在 Godzilla 自带的 FilterShell 插件中可以看到注入的 Filter 内存马

![img11.png](img/img11.png)

如果想要删除注入的 Suo5 内存马, 需要在 FilterShell 插件中操作

### 注入 Tomcat Servlet 内存马

需要指定 urlPattern (servletPath), 注意该参数必须指定且不能与已有的 Servlet 名称冲突

![img12.png](img/img12.png)

在 Godzilla 自带的 ServletManage 插件中可以看到注入的 Servlet 内存马

![img13.png](img/img13.png)

同样, 如果想要删除注入的 Suo5 内存马, 需要在 ServletManage 插件中操作

### 注入 WebLogic Filter 内存马

需要指定 urlPattern

目前不支持卸载 WebLogic Filter, 待解决

![img15.png](img/img15.png)

### 注入 Jetty Filter 内存马

需要指定 urlPattern

目前不支持卸载 Jetty Filter, 待解决

![img16.png](img/img16.png)

### 注入 Resin Filter 内存马

需要指定 urlPattern

目前不支持卸载 Resin Filter, 待解决

![img17.png](img/img17.png)

### 注入 JBoss/WildFly Filter 内存马

需要指定 urlPattern

目前不支持卸载 JBoss/WildFly Filter, 待解决

![img18.png](img/img18.png)

## Compile

GitHub Releases 页面提供了基于 JDK8 编译的 jar 包

当然你也可以选择自己手动编译

打开 IDEA 的项目结构, 点击 模块, 手动导入 godzilla.jar 和 Tomcat 依赖 (位于 Tomcat 路径的 `lib/` 目录)

![img1.png](img/img1.png)

点击 工件, 依照图示添加 JAR

![img2.png](img/img2.png)

默认回车即可

![img3.png](img/img3.png)

然后将输出布局中的以 "已提取" 开头的项全部删掉, 只留下 `Suo5MemShell 编译输出`

![img4.png](img/img4.png)

![img5.png](img/img5.png)

点击 构建 - 构建工件, 选择 `Suo5MemShell:jar` 并构建

![img6.png](img/img6.png)

![img7.png](img/img7.png)

编译好的 jar 位于当前项目的 `out` 目录

## Todo

- [x] 兼容更多中间件
- [ ] 插件体验优化
- [ ] 想到了再写
