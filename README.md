# 仓库说明（learn / java）

本仓库根目录即 **`learn/java`**，内按主题放置多个子目录与工程，**请勿**只保留单一目录。

| 路径 | 说明 |
|------|------|
| **`mybatis/`** | **Git 子模块** → 独立仓库 [`wxz6289/mybatis-submodule`](https://github.com/wxz6289/mybatis-submodule)（Spring Boot + MyBatis，`pom.xml` 与 `src/` 在该仓库根目录） |
| **`spring/`** | Spring 体系示例与 Gradle 工程 |
| **`AndroidBrowser/`** | Android 浏览器示例 |
| **`java`** | 子模块（Git submodule），Java 基础等独立仓库 |
| **`springboot`** | 子模块引用（见 `.gitmodules`） |

## 运行 MyBatis 示例

```bash
cd mybatis
cp .env.example .env   # 按需填写后
./mvnw spring-boot:run
```

文档见 `mybatis/doc/`、`mybatis/note/`（进入子模块目录后）。

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

父仓库中的 `mybatis` 目录记录的是**子模块 commit SHA**，日常改代码在子模块仓库完成。

克隆后若子模块为空，请执行：

```bash
git submodule update --init --recursive
```
