# SECoder 平台简介

## SECoder

![secoder](/assets/secoder.png)

### 软件工程开发平台 (SECoder)

- 帮助同学们顺利完成软件工程课程大作业的在线网站，提供了 GitLab、SonarQube 等用于更好管理开发流程的工具
- [https://sep.secoder.net](https://sep.secoder.net)

---

# SECoder

### 项目管理

- 提交数量和质量
- 任务数量
- 各仓库代码行数
- 注释比例
- 构建成功率
- 测试覆盖率

<img src="/assets/cake.jpg" style="position: absolute; top: 15%; right: 5%; height: 70%; width: auto;">

---

# SECoder

###

![dynos](/assets/dynos.jpg)

### 部署管理

- 对团队的容器进行各种管理操作
- 建立仓库时选择「启用部署」即可创建一个关联的容器

---

# SECoder

### 配置项

- 在开发时和正式部署时使用不同的配置是一种常见做法
- 然而，由于容器的易失性，一个容器在删除后其中所做的修改都将丢失
  - 这意味着每次都手动修改配置会很麻烦
- 可以通过配置项来简化这个流程
  - 配置项是只读的挂载项，可以用于存放各种配置文件
  - 配置项可以作为一个目录被挂载到容器中
  - 这样，在部署时将会自动使用挂载的配置
- 可参考文档中的 [配置挂载演示](https://thuse-course.github.io/course-index/deploy/secoder/#_12)

---

# SECoder

### 持久存储

- 数据库容器等需要在容器内保存数据
- 但同样由于容器的易失性，在容器重启时其中的数据将会丢失，因此我们需要一种能够持久保存数据的方法
- 持久存储与配置项类似，都可以挂载到容器的某一目录
  - 不同点在于持久存储是可写的，并且你不需要为其提供初始内容
  - 在不同的容器实例间保持数据
- 操作步骤与配置项类似
- 可参考 SECoder 帮助文档中的 [数据库教程](https://docs.secoder.net/service/deployer/tutorial-database/)
