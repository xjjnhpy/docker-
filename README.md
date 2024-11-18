# docker学习
## 列举镜像
docker images -a 

--rm 代表容器结束运行时，自动删除容器
docker commit 

假设你有一个正在运行的容器，你对其进行了一些更改，现在想要保存这些更改为一个新的镜像：

首先，找到你想要提交的容器的 ID 或名称：
bash
docker ps
使用 docker commit 命令创建一个新的镜像：
bash
docker commit -a "Your Name" -m "My new image" my-container my-repo:mytag
这里，my-container 是容器的名称或 ID，Your Name 是你的名字（作为作者），My new image 是提交信息，my-repo 是镜像仓库名，mytag 是标签。

现在，你可以使用 docker images 查看新创建的镜像：
bash
docker images
注意事项
docker commit 创建的镜像是基于当前容器的状态，包括文件系统的变化和环境变量的更改。
如果你想要基于一个现有的 Dockerfile 创建镜像，使用 docker build 而不是 docker commit。
docker commit 创建的镜像可能包含不需要的临时文件或配置，因此在生产环境中，通常推荐使用 Dockerfile 来创建镜像，以确保镜像的可重复性和一致性。
使用 docker commit 可以快速创建镜像，但请记住，最佳实践是使用 Dockerfile 来定义和创建镜像。
