```
# Substreams 数据解析项目：BSC & Solana Swap 事件

这个项目利用 **Substreams** 框架，成功解析了 **BSC Uniswap V3** 和 **Solana Raydium V4** 合约的 **Swap** 事件。

## 1. 任务概述 (Task Overview)

- **目标**: 解析特定链上合约的 **Swap** 事件，提取关键交易数据。
- **BSC 合约**: `0xd857e4a8fe599ed936157076674b2756d9df6fe8` (Uniswap V3)
- **Solana 合约**: `675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8` (Raydium V4)

---

## 2. BSC 部分：Uniswap V3 Swap 事件解析

### **实现路径**

1.  **项目初始化**: 遵循 [Substreams 官方文档](https://substreams.streamingfast.io/getting-started/quickstart) 创建项目。
2.  **代码实现**: 在 `lib.rs` 中，通过以下两个核心条件来筛选事件：
    -   **目标合约地址**: 过滤无关的交易。
    -   **目标事件类型**: 明确解析 `Swap` 事件。
3.  **运行命令**: 使用 `substreams run` 命令进行解析，并指定 BSC 网络端点。

### **解析成果**

**Swap** 事件数据已成功解析，结果保存在 `bsc_uniswap_v3/output.json` 文件中。

---

## 3. Solana 部分：Raydium V4 Swap 指令解析

### **实现路径**

1.  **合约侦察**: 在 `solscan.io` 上验证地址 `675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8`，确认其 `Public name` 为 **"Raydium Liquidity Pool V4"**。
2.  **项目创建**: 创建新的 Substreams 解析项目。
3.  **数据结构定义**: 在 `proto/mydata.proto` 中自定义要解析的交易数据结构。
4.  **代码编写**: 在 `lib.rs` 中编写事件解析代码，使用 `sol-transactions` 库处理 Solana 交易指令。

### **解析成果**

**Swap** 指令已成功解析，结果保存在 `solana_raydium_v4/output.json` 文件中。

---

## 4. 总结与思考 (Summary & Reflections)

这次挑战让我更深入地理解了 Substreams 的强大和灵活性。它是一个高度可定制的链上数据解析平台，能高效处理复杂的合约事件。同时，我也意识到，要熟练运用 Substreams 进行 Solana 项目解析，不仅需要扎实的 Rust 编程基础，还需要对 Solana 的交易结构有深刻的理解。

在这个过程中，Substreams 提供的在线开发环境和详细文档极大地提高了我的开发效率。最重要的是，我学会了如何利用 **AI 协作**，作为解决复杂编程挑战的有效工具。这只是一个验证性项目 (MVP)，未来可以根据更具体、更自定义的合约需求进一步优化和扩展。
```
