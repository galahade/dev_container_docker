# Python 开发容器

## 简介

本项目是为 `vscode dev container` 提供python开发环境的基础镜像。其中包括：

* `Python-3.11` 开发环境镜像(目前为python最新版本)

  * 文件名：`Dockerfile-3_11`
  * 镜像提供的软件：
    * Git
    * pipenv
  * [镜像依赖的原始镜像说明文档](https://github.com/microsoft/vscode-dev-containers/blob/v0.202.3/containers/python-3/README.md)
  * 构建命令：

    ```bash
    docker build --tag galahade/python-dev-container .
    docker build ---no-cache --tag galahade/python-dev-container .
    docker tag galahade/python-dev-container galahade/python-dev-container:v0.1
    ```

* `tqsdk2` 开发环境镜像(python-3.10), 由于天勤软件包的限制，该镜像由之前镜像基础上修改python版本而来。同时该镜像只能在 `x_86` 架构上构建，苹果M系列芯片不能运行`tqsdk2`
  * 文件名：`Dockerfile-tqsdk2`
  * 镜像提供的软件：
    * Git
    * pipenv
  * [镜像依赖的原始镜像说明文档](https://github.com/microsoft/vscode-dev-containers/blob/v0.202.3/containers/python-3/README.md)
  * 构建命令：

    ```bash
    docker build --tag galahade/python-dev-container-tqsdk2 .
    docker build ---no-cache --tag galahade/python-dev-container-tqsdk2 .
    docker tag galahade/python-dev-container-tqsdk2 galahade/python-dev-container-tqsdk2:v0.1
    ```

* `python` and `Docker` 开发环境镜像, 目前如果想在开发环境中即成docker命令，可以在`.devcontainer.json`文件中使用 dev container future：`ghcr.io/devcontainers/features/docker-outside-of-docker:1`. 该镜像文件为了将安装docker的命令记录下来，并没有实际使用。
  * 文件名：`Dockerfile-3_docker`
  * 镜像提供的软件：
    * docker-ce-cli
    * docker-compose
    * Git
    * pipenv
  * [镜像依赖的原始镜像说明文档](https://github.com/microsoft/vscode-dev-containers/blob/v0.202.3/containers/python-3/README.md)

## 参考

[How to set up a perfect Python project](https://sourcery.ai/blog/python-best-practices/)

[A perfect way to Dockerize your Pipenv Python application](https://sourcery.ai/blog/python-docker/)

[Best Practices: Authoring a Dev Container Feature
](https://containers.dev/guide/feature-authoring-best-practices)
