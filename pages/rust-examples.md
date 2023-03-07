---
transition: slide-up
---

# Rust 在前端领域的应用与实践

- 桌面应用开发：Rust 可以用于开发跨平台和性能优异的桌面应用，例如：
  - [tauri](https://tauri.app/)：一个使用 Rust 和 Web 技术（HTML/CSS/JS）开发轻量级和安全的桌面应用框架，可以打包成小于 1 MB 的二进制文件
  - iced：一个使用 Rust 开发简洁和响应式的图形用户界面（GUI）框架，支持 WebAssembly 和原生平台

- NodeJS：Rust 可以用于开发与 NodeJS 集成或替代的模块或应用，例如：
  - neon：一个使用 Rust 开发并与 NodeJS 进行互操作的框架，可以提升 NodeJS 应用的性能和安全性
  - [deno](https://deno.land/)：一个使用 Rust 和 TypeScript 开发的新一代 NodeJS 替代品，提供了更现代化和安全化的 API 和特性
  - [napi-rs](https://napi.rs/)：一个使用 Rust 开发并与 NodeJS 进行互操作的框架，可以利用 NodeJS 的 N-API 接口来编写高性能的原生模块
  - [yew](https://github.com/yewstack/yew)：一个使用 Rust 和 WebAssembly 开发单页应用（SPA）的框架，类似于 React，支持组件化和虚拟 DOM

<!--
1. 操作系统：Rust 在操作系统领域的应用包括 Redox OS、Tock OS 等。Redox OS 是一个完全用 Rust 开发的操作系统，其目标是成为安全、稳定、分布式的操作系统。Tock OS 是一个面向 IoT 设备的操作系统，它使用 Rust 开发，提供了一种可靠的嵌入式应用程序开发方式。
2. 嵌入式系统：Rust 在嵌入式系统领域的应用包括 Real-Time For the Masses (RTFM)、Drone OS 等。RTFM 是一个基于 Rust 的嵌入式系统开发框架，它提供了一种基于任务的并发模型和可预测性的实时性能。Drone OS 是一个用 Rust 编写的嵌入式系统开发框架，它提供了一个可扩展的构建系统、一个轻量级任务运行时和一组库。
3. 网络服务：Rust 在网络服务领域的应用包括 Actix、Tokio、Rocket 等。Actix 是一个用 Rust 编写的 Web 应用程序框架，它提供了高性能、可伸缩性和可靠性。Tokio 是一个用 Rust 编写的异步运行时，它提供了高性能、可扩展性和灵活性。Rocket 是一个用 Rust 编写的 Web 框架，它提供了易于使用、高性能和安全的特性。
4. 游戏引擎：Rust 在游戏引擎领域的应用包括 Amethyst、GGEZ、Piston 等。Amethyst 是一个用 Rust 编写的 2D 和 3D 游戏引擎，它提供了高性能、可扩展性和灵活性。GGEZ 是一个用 Rust 编写的 2D 游戏引擎，它提供了易于使用和轻量级的特性。Piston 是一个用 Rust 编写的游戏引擎，它提供了一个简单、易于使用的 API 和可扩展的特性。
5. Web 开发：Rust 在 Web 开发领域的应用包括 Rocket、Actix-web、Warp 等。Rocket 是一个用 Rust 编写的 Web 框架，它提供了易于使用、高性能和安全的特性。Actix-web 是一个用 Rust 编写的 Web 应用程序框架，它提供了高性能和可伸缩性。Warp 是一个用 Rust 编写的 Web 服务框架，它提供了易于使用和高性能的特性。
6. 工具开发：Rust 在工具开发领域的应用包括 Rust 编译器、Cargo、Rustfmt 等。Rust 编译器是 Rust 语言的官方编译器，它使用 Rust 语言自身编写，提供了高性能和可靠性。Cargo 是 Rust 的官方构建工具和包管理器，它提供了易于使用、可靠性和安全性。Rustfmt 是 Rust 的官方格式化工具，它提供了一种一致的代码格式化方式。
7. 数据科学：Rust 在数据科学领域的应用包括 Polars、DataFusion、TensorBase 等。Polars 是一个用 Rust 编写的数据操作和分析库，它提供了类似于 Pandas 的 API 和高性能。DataFusion 是一个用 Rust 编写的分布式 SQL 引擎，它提供了高性能、可伸缩性和可扩展性。TensorBase 是一个用 Rust 编写的分布式 SQL 引擎，它提供了高性能和可伸缩性
-->
