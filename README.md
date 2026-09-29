# 每日签到系统

一个基于 JSP 的简单签到页面示例，可在 IntelliJ IDEA 中使用 Tomcat 11 运行。页面收集姓名和学号，并在提交后显示签到成功提示。

## 功能

- 提供中文签到页面，适配桌面和手机屏幕。
- 输入姓名和学号后进行浏览器端必填校验。
- 点击“立即签到”后在当前页面显示成功提示，并禁用提交按钮。

> 当前示例只在浏览器中显示签到结果，不会把签到信息保存到服务器或数据库。

## 技术栈

- Java 21
- Jakarta Servlet API 6.1
- JSP
- Maven
- Apache Tomcat 11

## 环境要求

- JDK 21 或兼容的更高版本
- IntelliJ IDEA（支持 Maven 和 Tomcat 部署）
- Apache Tomcat 11

## 在 IDEA 中运行

1. 在 IDEA 中打开项目根目录。
2. 等待 IDEA 导入 Maven 项目并完成依赖下载。
3. 在 **Run → Edit Configurations** 中添加 **Tomcat Server → Local**。
4. 在 **Deployment** 标签页添加项目的 `demo1:war exploded` 部署项。
5. 将应用上下文路径设置为 `/demo1`（也可以按需修改）。
6. 启动 Tomcat，在浏览器中打开 `http://localhost:8080/demo1/`。

## 使用 Maven 打包

Windows：

```powershell
.\mvnw.cmd clean package
```

macOS / Linux：

```bash
./mvnw clean package
```

打包成功后，WAR 文件位于 `target/demo1-1.0-SNAPSHOT.war`。将该文件部署到 Tomcat 11 后即可访问签到页面。

## 项目结构

```text
demo1/
├── src/main/java/com/zjut/demo1/HelloServlet.java  # 示例 Servlet
├── src/main/webapp/
│   ├── WEB-INF/web.xml                             # Web 应用配置
│   └── index.jsp                                   # 签到页面
├── pom.xml                                         # Maven 配置
└── README.md                                       # 项目说明
```
