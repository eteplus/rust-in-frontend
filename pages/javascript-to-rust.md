---
transition: slide-up
---

# 从 JavaScript 到 Rust

JavaScript 是使用最广泛的编程语言，存在于每个有浏览器的设备上。

在过去的十年中，围绕着 JavaScript 已经建立了一个庞大的生态系统。

如 [Webpack](https://webpack.js.org/)、[Babel](https://babeljs.io/)、[Terser](https://terser.org/)、[Prettier](https://prettier.io/)、[ESlint](https://eslint.org/) 等。通过这些工具，数以百万计的代码被编写出来，甚至更多的 bug 被修复，从而为今天的 Web 应用提供了基础。所有这些工具都是用 JavaScript 或 TypeScript 编写的。

目前已经做的很不错了，但我们对 JS 的优化基本已经达到顶峰。

因此，这激发了一些新工具的诞生，旨在大幅提高 Web 构建的性能。

<div v-click class="grid grid-cols-4 gap-4 py-8">
  <img src="https://swc.rs/logo.png" />
  <img src="https://parceljs.org/avatar.66e613b2.avif" />
  <img src="https://storage.googleapis.com/zenn-user-upload/c71a7yacm76cuj7croaswi7ofdbt" />
  <img src="https://rome.tools/img/social-logo.png" />
</div>

---
transition: slide-up
layout: two-cols
class: px-2
---

-  [SWC](https://swc.rs/)

  SWC 是一个可扩展的基于 Rust 的前端构建工具，可用于编译（compilation）、压缩（minification）、打包（bundling）等。你可以调用它来执行代码转换（无论是内置的还是自定义的）。

- [Parcel](https://parceljs.org/)

  支持以 HTML 作为入口的零配置构建工具，Parcel 支持多种开箱即用的语言和文件类型，从 HTML、CSS 和 JavaScript 等 Web 技术到图像、字体、视频等资产。当您使用默认不包含的文件类型时，Parcel 将自动为您安装所有必要的插件和开发依赖项。Parcel 的 JavaScript 编译器和源映射是建立在 SWC 编译器之上的，在 SWC 之上，Parcel 实现了依赖项收集、捆绑、摇树优化、热重载等。

- [esbuild](https://esbuild.github.io/)

  esbuild 创建于 2020 年 1 月，一个代码打包和压缩的工具，它是用 Go 写的，比当今的工具快 10 到 100 倍。

::right::


- [Rome](https://rome.tools/)

  [Rome](https://rome.tools/) 创建于 2020 年 8 月，包含 linter、compiler、bundler、test runner 以及其它东西，适用于 JavaScript、TypeScript、HTML、JSON、Markdown 和 CSS 。他们的目标是取代和统一整个前端开发工具链。它是由 [Sebastian](https://twitter.com/sebmck) 创建的，他是 Babel 的创建者。

  Rome 目前是用 TypeScript 编写的，在 Node.js 上运行。但他们现在正致力于 用 Rust 重写。

<!--
我试图创建一个构建工具：

A）能够在一个合理的场景（bundler JavaScript，TypeScript，也许还有CSS）中工作得很好。

B）能够重新定义社区对构建工具速度的期望。对于JS快速构建工具来说，到底什么才是快？在我看来，我们目前的工具都太慢了。

—— Evan，Creator of esbuild

在 esbuild 发布之前，用系统编程语言（如 Go 和 Rust ）构建 JavaScript 工具是相当小众的。因此在我看来，esbuild 激发人们对于让开发工具更快的广泛兴趣。Evan 选择了使用 Go：

Rust版本也许可以通过足够的努力使其以同等速度工作。但在高层次上，Go 的工作方式更令人愉快。这是一个 side project ，所以它对我来说必须要有乐趣。

—— Evan，Creator of esbuild

有人认为 Rust 可以表现得更好，但两者都可以实现 Evan 最初的目标，即影响社区：

即使只是进行了基本的优化，Rust也能够胜过超手工调整的 Go 版本。这是一个巨大的证明，与我们不得不对 Go 的深入研究相比，用Rust编写高效程序是多么容易。

—— Discord

-->

---
transition: slide-left
layout: two-cols
class: px-2
---

# JavaScript 与 Rust 区别


##### 不同之处

<br />

  - Rust 是一门静态强类型语言，它要求每个变量和表达式都有确定的类型，并在编译期进行严格的检查和推断，Javascript 是一门动态弱类型语言，它没有明确的类型声明和检查机制，而是在运行时进行隐式转换或报错。

  ```javascript
  // Javascript
  let x = "hello"; // x is a string
  x = x + 1; // x is now a number (NaN)
  x = true; // x is now a boolean (true)
  ```

  ```rust
  // Rust
  let mut x = "hello"; // x is a string (&str)
  //x = x + 1; // compile error: no implementation for `&str + {integer}`
  x = "world"; // ok: reassigning a string to a string
  //x = true; // compile error: mismatched types
  ```
<br />

  - Rust 使用所有权和借用机制来管理内存，而 JavaScript 使用垃圾回收（garbage collection）机制。

::right::

  - Rust 支持泛型（generic）、枚举（enum）、结构体（struct）、元组（tuple）等特性，而 JavaScript 不支持。
  - Rust 支持特征（trait）、生命周期（lifetime）、宏系统（macro system）等高级特性，而 JavaScript 不支持。
  - Rust 使用分号来结束表达式，而 Javascript 可以省略分号。

<br />

##### 相同之处

- 都有一个现代化的包管理系统。JavaScript 有 npm，Rust 有 Cargo。

    <img src="/cargo-npm.webp" class="w-80%" />

- 都支持函数式编程和面向对象编程的范式，并提供了闭包、迭代器等特性。

