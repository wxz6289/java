# 仓库说明（learn / java）

本仓库根目录即 **`learn/java`**，内按主题放置多个子目录与工程，**请勿**只保留单一目录。

| 路径 | 说明 |
|------|------|
| **`base/`** | **Git 子模块** → [`wxz6289/base`](https://github.com/wxz6289/base)（Java 基础 / 通用资料） |
| **`mybatis/`** | **Git 子模块** → [`wxz6289/mybatis`](https://github.com/wxz6289/mybatis)（Spring Boot + MyBatis 工程本体） |
| **`spring/`** | Spring 体系示例与 Gradle 工程 |
| **`AndroidBrowser/`** | Android 浏览器示例 |
| **`springboot`** | 子模块引用（见 `.gitmodules`；`spring/springboot` 路径需与仓库实际一致） |

> 说明：父仓库已更名为 **`wxz6289/java`** 后，原先指向 `wxz6289/java.git` 的嵌套子模块 **`java/`** 会与父仓库 URL 冲突，已从本聚合仓移除；「Java 基础」类内容请放在 **`base/`** 子模块仓库 [`wxz6289/base`](https://github.com/wxz6289/base)。

## 运行 MyBatis 示例

```bash
cd mybatis
cp .env.example .env   # 按需填写后
./mvnw spring-boot:run
```

文档见 `mybatis/doc/`、`mybatis/note/`（进入子模块目录后）。

### 在 `base` 子模块里开发与推送

```bash
cd base
git checkout main
git add -A && git commit -m "docs: ..." && git push origin main
cd ..
git add base && git commit -m "chore: bump base submodule" && git push origin main
```

### 在 `mybatis` 子模块里开发与推送

```bash
cd mybatis
git checkout main
# 修改、提交到子模块自己的仓库
git add -A && git commit -m "feat: ..." && git push origin main
# 回到父仓库，更新子模块指针
cd ..
git add mybatis
git commit -m "chore: bump mybatis submodule"
git push origin main
```

父仓库（**[`wxz6289/java`](https://github.com/wxz6289/java)**）中的 **`base/`**、**`mybatis/`** 记录的是各子模块的 **commit SHA**，日常改代码在对应子仓库完成。

克隆后若子模块为空，请执行：

```bash
git clone --recurse-submodules git@github.com:wxz6289/java.git
# 或
git submodule update --init --recursive
```
