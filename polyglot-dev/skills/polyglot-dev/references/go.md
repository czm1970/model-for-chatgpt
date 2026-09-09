# Go

- 从 go.mod、go.work、toolchain 和 CI 确认版本、模块边界及工作区，不随意修改 module 路径或执行依赖升级。
- 对修改的 Go 文件运行 gofmt；按范围执行 go test，必要时使用 go vet。go test ./... 仅覆盖当前模块时，多模块仓库应分别处理相关模块。
- 外部调用传播 context，提供超时或取消路径；明确 goroutine 的退出条件及 channel 的关闭责任，防止泄漏和死锁。
- 保留 error 的上下文和可识别性，遵循项目的包装约定；注意带类型的 nil 接口与零值行为。
- 并发改动在平台支持时考虑 go test -race；无需为普通局部改动运行全仓压力测试。不要无理由运行 go mod tidy，它可能改变无关依赖。
