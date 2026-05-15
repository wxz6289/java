# 仓库说明（learn / java）

本仓库根目录即 **`learn/java`**，内按主题放置多个子目录与工程，**请勿**只保留单一目录。

| 路径 | 说明 |
|------|------|
| **`mybatis/`** | Spring Boot + MyBatis 实践工程（Maven：`pom.xml`、`src/` 在此目录下） |
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

文档见 `mybatis/doc/`、`mybatis/note/`。

## 子模块

克隆后若子模块为空，请执行：

```bash
git submodule update --init --recursive
```
