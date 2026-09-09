# Java

- 从 pom.xml、Gradle 配置、wrapper 和 toolchain 确定 JDK 与构建方式，不因为本机有更新 JDK 就改变目标版本。
- Maven 项目优先使用 mvnw / mvnw.cmd；Gradle 项目优先使用 gradlew / gradlew.bat。按模块运行已有测试，必要时再运行项目级验证。
- 沿用已有 Spring、Jakarta 或其他框架约定，注意 javax 与 jakarta 的版本边界；无框架项目不默认引入 Spring。
- 资源生命周期使用项目认可的关闭方式，阻塞 I/O 不放进异步事件循环。异常映射保持 API 契约，不能吞掉错误后返回成功。
- 涉及事务时检查边界与回滚条件；涉及并发时验证共享状态，不把集合替换为并发集合当作完整的原子性保证。
