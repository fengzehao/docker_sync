# docker_sync
通过Github工作流来建立个人镜像加速站，详细可以参考[此文章](https://chenpi-sakura.github.io/posts/how-to-solve-docker-pull-failed/)

# 示例操作
首先fork这个项目[docker_sync](https://github.com/Chenpi-Sakura/docker_sync)，相关的`Action`代码可以参考项目`.github\workflows`目录下的yml文件

然后按照顺序点击 `Settings` -> `Secrets and variables` -> `Actions`->`New repository secret`

![](https://caipiischenpi.dpdns.org/PicGo/docker-sync-1.png)

>这里我们以拉取镜像`mcr.microsoft.com/devcontainers/jekyll:2-bullseye`和命名空间`saku`为例

需要设置以下参数

* `ALIYUN_USERNAME`: 你的阿里云 UserID。
* `ALIYUN_PASSWORD`: 第一步里设置的 Registry 独立密码。
* `ALIYUN_NAMESPACE`: 第一步中设置的命名空间
* `ALIYUN_REGISTRY`: 控制台概览中的公网域名

![](https://caipiischenpi.dpdns.org/PicGo/docker-sync-2.png)

填写后点击`Add secret`按照下图添加，添加以上四个Secret。

![](https://caipiischenpi.dpdns.org/PicGo/docker-sync-3.png)

配置完成后，去 GitHub 仓库的 `Actions` 页面，选中 `Mirror Docker Image to Aliyun`，点击 `Run workflow`，填写相关配置，再点击`Run workflow`。

![](https://caipiischenpi.dpdns.org/PicGo/docker-sync-4.png)

等待拉取完毕，

![](https://caipiischenpi.dpdns.org/PicGo/docker-sync-5.png)
![](https://caipiischenpi.dpdns.org/PicGo/docker-sync-6.png)

此时`Action`界面显示成功，控制台中也出现了相应的仓库
