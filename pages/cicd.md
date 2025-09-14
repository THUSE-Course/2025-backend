# 持续集成与持续部署简介

## 持续集成与持续部署

### 持续集成 (Continuous Integration/CI)

- 在代码构建过程中持续地进行代码的集成、构建、以及自动化测试等
- 可以在代码提交的过程中通过单元测试等尽早地发现引入的错误

### 持续部署 (Continuous Deployment/CD)

- 在代码构建完毕后迅速将新版本部署上线
- 有利于快速迭代并交付产品

---

# 持续集成与持续部署

### 为什么需要 CI/CD

- 自动化：不用手动执行测试、部署等
- 标准化：定义一套固定的流程，避免人为部署带来的错误
- 尽早发现错误：避免长时间后难以定位问题根源

---

# GitLab CI/CD

### GitLab CI/CD

- 一套基于 GitLab 的 CI/CD 系统
- 可以让开发人员通过 .gitlab-ci.yml 在项目中配置 CI/CD 流程
- 在每次 push 到仓库后，系统都可以自动（或手动）地执行 CI/CD 所定义的操作

---

# 基本概念

###

![pipeline](/assets/pipeline.jpg)

---

# 基本概念

### 作业 (Job)

- CI/CD 流程的最小执行单元
- 包含了一系列需要执行的命令
- 需要指定一个 Docker 镜像，在执行 CI/CD 时将会基于此镜像运行一个容器，在其中执行命令
- 成功状态将取决于其最后一条命令的返回值

---

# 基本概念

### 阶段 (Stage)

- CI/CD 流程划分为多个阶段分别进行，每个阶段可以包含一个或多个作业
- 同一个阶段的多个作业可以并行执行
- 一个阶段的所有作业均成功执行后，才会执行下一个阶段的作业

---

# 基本概念

### 流水线 (Pipeline)

- 多个阶段顺序连接组成一个流水线
- 将代码推送到远程仓库或是发起合并请求时，GitLab 会基于该版本的代码执行流水线

---

# .gitlab-ci.yml

### 镜像指定

```yaml
image: python:3.9
```

### 阶段定义

```yaml
stages:
  - build
  - test
  - deploy
```

### 作业定义

```yaml
style-test:
  stage: test
  before_script:
    - pip install pylint
  script:
    - pylint **/*.py
```
