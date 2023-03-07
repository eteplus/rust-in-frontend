---
transition: slide-up
layout: two-cols
class: px-2
---

# 为什么是 Rust？

Rust 有以下几个优势：

<span class="text-lg font-bold text-amber">高性能</span>
- Rust 可以利用 WebAssembly 技术，在浏览器中运行接近原生速度的代码。
- Rust 还可以提供更好的并发支持，利用多核处理器和异步 I/O 来提升性能。

<span class="text-lg font-bold text-amber">安全</span>
  - Rust 通过所有权（ownership）、借用（borrowing）和生命周期（lifetime）等机制在编译期自动插入内存释放逻辑来实现内存管理，可以避免常见的内存错误，如空指针解引用、缓冲区溢出、内存泄漏等。
  - Rust 还可以保证数据竞争安全，避免多线程环境下的数据不一致问题。

::right::

<span class="text-lg font-bold text-amber">跨平台</span>
  - Rust 可以在不同的操作系统上运行，并且可以与 Javascript 和其他语言进行交互。
  - Rust 还可以用于开发桌面应用、移动应用等场景。

<span class="text-lg font-bold text-amber">生产力</span>
  - Rust 是一门现代的语言，它拥有强大的类型系统、模块化结构、表达力强的语法糖、丰富的标准库和生态系统等特点。
  - Rust 还支持元编程、宏系统、测试框架等高级特性。
  - Rust 拥有出色的文档、友好的编译器和清晰的错误提示信息，还集成了一流的包管理器和构建工具，智能地自动补全和类型检验的多编辑器支持，以及自动格式化代码等。

---
transition: slide-left
---

# 🚀 高性能、内存安全和更小的内存占用

<div class="grid grid-cols-[2fr_2fr] gap-4">

  <div>

  [Rust 所有权转移的代码示例](https://play.rust-lang.org/?version=stable&mode=debug&edition=2021&gist=4d4a822c9dcad71466f8d1c67c4282ec)：

  <div @click="$slidev.nav.next">

  ```rust
  fn main() {
      let text_ownership = String::from("Hello Rust!");
      // address: 0x5648a21129d0
      println!("address: {:p}", text_ownership.as_ptr());
      // 所有权被转移
      let text_ownership_move = text_ownership;
      // 编译失败！text_ownership 已经被释放，无法再使用
      println!("{}", text_ownership);
      // address: 0x5648a21129d0
      println!("address: {:p}", text_ownership_move.as_ptr());
      println!("{}", text_ownership_move);
  }
  ```

  </div>

  </div>

  <div v-click="1">

  编译结果：

  <img src="/rust-ownership-build-error.png" />

  </div>
</div>

- 在一项比较[REST API 性能的基准测试](https://medium.com/sean3z/rest-api-node-vs-rust-c75aa8c96343)中（Rust 使用 [Rocket](https://rocket.rs/)，Node.js 使用 [Restify](http://restify.com/)），Rust 每秒处理 **72,000** 个请求，而 Node.js 为 **8,000** 个，空闲时使用的内存大约为 **1MB**，而 Node.js 为 **19MB**。

- 其他测试数据可以参考 [Web Frameworks Benchmark](https://web-frameworks-benchmark.netlify.app/compare?f=actix,koa,fastify,express)

<!--
Rust 有以下特点：

- **零成本抽象**：Rust 可以在不牺牲性能的情况下提供高级的抽象
- **内存安全**：Rust 通过所有权、借用和生命周期等机制来避免空指针、悬垂指针、数据竞争等常见的内存错误
- **类型安全**：Rust 的类型系统可以在编译期检查出类型错误、空值错误、匹配错误等，并支持泛型和特征等高级特性
- **表达力**：Rust 的语法和语义可以让开发者用简洁和清晰的方式表达复杂的逻辑
- **生态系统**：Rust 拥有一个庞大而活跃的社区，以及丰富而高质量的第三方库

- Rust 通过所有权、借用和生命周期等机制在编译期自动插入内存释放逻辑来实现内存管理。由于没有了垃圾回收产生的运行时开销，Rust 整体表现的速度惊人且内存利用率极高，其内存占用也较少，这使得 Rust 成为编写高性能、低延迟的前端应用的理想选择。
- Rust 的所有权系统可以确保内存安全，这减少了在编写复杂前端代码时出现的潜在内存泄漏和空指针问题的风险。

text_ownership.as_ptr() 打印的地址是 text_ownership 表示的堆上对象的实际地址
-->
