---
transition: slide-up
layout: two-cols
class: px-4
---

# Rust 和 WebAssembly

<img src="https://webassembly.org/css/webassembly.svg" />

WebAssembly 是一种新的代码类型，可以在现代浏览器中运行。它是一种低级的类汇编语言，具有紧凑的二进制格式，可以接近原生的性能运行。

WebAssembly 的设计目标是保持网页的无版本、特性测试和向后兼容的特性。WebAssembly 也支持非网页的嵌入。例如，[Wasmer](https://wasmer.io/)是一个使用 WebAssembly 作为服务器端容器化技术的项目。

::right::

Rust 提供了 wasm-bindgen 和 wasm-pack 等工具来简化 WebAssembly 的开发流程。

- [wasm-bindgen](https://github.com/rustwasm/wasm-bindgen)：一个使用 Rust 开发 WebAssembly 模块并与 JavaScript 进行互操作的工具库，可以自动生成绑定代码和类型定义

```rust
use wasm_bindgen::prelude::*;
#[wasm_bindgen]
pub fn fibonacci(n: u32) -> u32 {
    match n {
        0 | 1 => n,
        _ => fibonacci(n - 1) + fibonacci(n - 2),
    }
}
```

- [wasm-pack](https://github.com/rustwasm/wasm-pack)：一个使用 Rust 开发并发布 WebAssembly 包到 npm 的工具，可以自动处理依赖和构建流程
  - `new`：使用模板生成一个新的 Rust Wasm 项目
  - `build`: 从 rustwasm crate 生成一个 npm wasm pkg
  - `test`：运行浏览器测试
  - `pack` 和 `publish`：创建压缩包，发布到镜像仓库


---
transition: slide-left
---

# Rust 和 WebAssembly 的应用场景

在前端领域，Rust 和 WebAssembly 的组合可以应用于以下场景：
1. 游戏开发：Rust 和 WebAssembly 可以用于编写高性能、交互式的 Web 游戏。
2. 图形处理：Rust 和 WebAssembly 可以用于在 Web 中进行实时的图形处理，如三维渲染、图像处理等。
3. 计算密集型任务：Rust 和 WebAssembly 可以用于在 Web 中进行计算密集型的任务，如科学计算、机器学习等。
4. 应用程序性能优化：Rust 和 WebAssembly 可以用于编写 Web 应用程序的核心功能，以提高应用程序的性能和安全性。

<br />

##### 案例

- Figma 是一款在线的设计工具，它利用了 Webassembly 的高性能和跨平台的特性，让用户可以在浏览器中进行复杂的图形操作¹。Figma 还使用了 Rust 语言来编写服务器端的代码，从而提高了服务的稳定性和效率
    - [Figma is powered by WebAssembly](https://www.figma.com/blog/webassembly-cut-figmas-load-time-by-3x/)
    - [Rust in Production at Figma](https://www.figma.com/blog/rust-in-production-at-figma/)


<!--
Rust 的优势有：
- Rust 可以在不同的平台上运行，也可以用作函数式、静态类型和系统编程语言¹。
- Rust 比它继承的语言更安全，因为它强制使用所有权和借用机制来管理内存²。
- Rust 不需要额外的软件来编译 Rust 程序，只需要操作系统¹。
- Rust 的代码是可重用的，可以方便地创建模块和库¹。
- Rust 支持复杂的数据类型，如元组、枚举、结构体和特征¹。

Rust 的缺点有：
- Rust 有一个陡峭的学习曲线，因为它有很多独特的概念和规则²。
- Rust 的编译时间较长，因为它进行了很多检查和优化²。
- Rust 的生态系统还不够成熟，一些库和工具可能还不完善或缺乏文档⁴。

webassembly 的优势有：
- webassembly 的文件很小，可以让用户更快地加载网页⁵。
- webassembly 可以运行接近原生代码的速度，而不需要安装、本地安全问题或占用磁盘空间⁵。
- webassembly 可以使用与 JavaScript 相同的 web API⁵。
- webassembly 可以将多种编程语言编译成机器码⁵。
- webassembly 的二进制文件可以让人类更容易地调试，因为它们可以转换成文本格式⁵。
- webassembly 支持服务器端提前编译，使得它比 JavaScript 更快⁶。

webassembly 的缺点有：
- webassembly 还需要一个小型的运行时环境来加载客户端，并且可能会受到浏览器兼容性的限制⁶。
- webassembly 还没有支持垃圾回收、异常处理、多线程等一些重要的特性⁷[8]^。
- webassembly 还没有一个统一的标准库或包管理器，开发者需要自己选择或创建合适的工具链和依赖项⁸
 -->
