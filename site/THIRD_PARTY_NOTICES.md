# 第三方依赖与资源

精确安装版本与完整依赖树见 `package-lock.json`；`node_modules` 和编译输出不提交。安装包随附的版权声明与许可应予保留。

| 依赖 | 本版版本 | 安装包声明的许可 | 用途 |
|---|---|---|---|
| React / React DOM | 19.3.1 | MIT | 学习界面 |
| chess.js | 1.4.0 | BSD-2-Clause | 棋规与 PGN |
| Three.js | 0.180.0 | MIT | WebGL 棋盘 |
| Lucide React | 0.468.0 | ISC | 界面图标 |
| stockfish npm / stockfish.js | 19.0.1 / 引擎 19 | GPL-3.0 | Node 子进程／浏览器 Worker 运行 Lite single-thread WASM |
| Vite / TypeScript / Prettier | 见锁文件 | MIT / Apache-2.0 / MIT | 构建、检查、格式化 |

Stockfish 包来源：[stockfish.js](https://github.com/nmrugg/stockfish.js)，安装的 GPL 许可原文位于 `node_modules/stockfish/Copying.txt`，本项目保留副本 `third-party/stockfish-GPL-3.0.txt`。对应版本的源代码和构建说明以安装包 README 与上游版本发布为准。浏览器Demo的发布包另附对应版本源码、Lite网络、校验值与构建入口，详见下文；未制作桌面独立安装包。

早期原型及导航图标中的棋子 SVG 来自 Font Awesome Free；SVG 图标采用 CC BY 4.0，归属及原文见 `prototype/assets/README.md`、`prototype/assets/icons/LICENSE.txt`。本项目保留了相应声明。`public/favicon.ico` 是同一马棋子图标的薄荷绿色、多尺寸 ICO 转换版本。

自然探索风格的机器人、棋盘场景和课程插画复用已有项目生成资源，说明见 `prototype/assets/README.md`。程序化 3D 棋子由本版代码生成。

当前本地MVP的2D棋盘及升变面板使用项目内手绘矢量棋子组件 `app/ChessPiece.tsx`；根据传统Staunton棋子的识别特征设计，未复制竞品图片素材。


浏览器Demo新增：`@noble/hashes`（MIT，精确版本见锁文件）用于保持Node与浏览器SHA-256种子选择一致；`fake-indexeddb`（Apache-2.0，仅测试）用于事务与并发回归。Demo引擎文件未修改，来自锁定的stockfish@19.0.1。构建产物`engine/`包含GPL许可、上游README、对应tag的完整源码归档及Lite网络；校验值与构建入口见同目录`SOURCES.md`，原始来源为[Stockfish.js源码](https://github.com/nmrugg/stockfish.js)与[19.0.1包](https://www.npmjs.com/package/stockfish/v/19.0.1)。源码材料也保存在项目`third-party/`，构建时校验后复制；本项目不把Stockfish引擎重新声明为MIT。


Node教练工具链新增 `@modelcontextprotocol/client@2.4.0`（Apache-2.0），来源为[官方TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)。保留安装包许可于 `third-party/mcp-client-Apache-2.0.txt`；其传递依赖和版本见锁文件。该客户端仅用于服务端只读MCP，不包含在Pages浏览器代码中。
