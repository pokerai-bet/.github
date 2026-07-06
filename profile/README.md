<div align="center">

# Pokerai API

**Solver-grade GTO strategy for 6-max No-Limit Hold'em — over HTTP.**

[Docs](https://pokerai.bet/docs.en) · [API Reference](https://pokerai.bet/reference) · [OpenAPI](https://pokerai.bet/openapi.yaml) · [llms.txt](https://pokerai.bet/llms.txt) · [Pricing](https://pokerai.bet/pricing) · [Get a free key →](https://pokerai.bet/login)

</div>

---

Mixed-frequency GTO strategy for **every street** of 6-max No-Limit Hold'em. Preflop and flop come from **millions of presolved solutions** served in milliseconds; turn and river are **solved on demand** on a real-time solver pool. Every request is **stateless and self-contained** — you send the spot, the API returns the strategy. It does not return a single "best" move; it returns the **frequency of each action**, so you randomize per your own strategy.

### One call

```bash
curl -s https://pokerai.bet/v1/gto/preflop \
  -H "Authorization: Bearer $POKERAI_API_KEY" -H "Content-Type: application/json" \
  -d '{"hole_cards":"AhKh","positions":{"hero":"MP"},
       "preflop_actions":[{"position":"UTG","action":"raise","amount":3}]}'
```
```json
{"hole_cards":"AhKh","situation":"Raise",
 "strategy":[{"action":"raise","frequency":1,"amount_bb":9,"sizing_pot":0.8}]}
```

> Hero (MP) with AhKh facing a UTG open: raise 100% of the time, to 9bb.

### Official clients

| Package | Registry | Install |
|---|---|---|
| [`pokerai-bet`](https://pypi.org/project/pokerai-bet/) | PyPI · Python | `pip install pokerai-bet` |
| [`@pokerai/client`](https://www.npmjs.com/package/@pokerai/client) | npm · TS/JS | `npm install @pokerai/client` |
| [`@pokerai/mcp`](https://www.npmjs.com/package/@pokerai/mcp) | npm · MCP server | `npx @pokerai/mcp` — GTO as tools for LLM agents |

Typed, auto-generated from the [OpenAPI spec](https://pokerai.bet/openapi.yaml) — always in sync with the API.

### Free tier

**1,000 presolved lookups + 25 real-time solves per month, no credit card.** → [Get a key](https://pokerai.bet/login)

### Built with it

**Counterplay (过招)** — a real-time GTO trainer for iOS built entirely on Pokerai API: every hand is played against pure-GTO opponents and every decision is graded against the frequencies these endpoints return.

### Acceptable use

Training, coaching, hand review, study, and research. **Real-time assistance (RTA) at real-money tables is prohibited** — see the [terms](https://pokerai.bet/terms).

---

<details>
<summary><b>简体中文</b></summary>

<br>

**面向 6-max 无限德州的 solver 级 GTO 策略,一次 HTTP 调用。**

每一街的混合频率 GTO 策略:preflop 与 flop 来自**数百万预解方案**(毫秒级),turn/river 在实时求解池上**按需求解**。每个请求**无状态、自包含**——发局面、拿策略;不给单一「最优手」,而是给每个动作的**频率**,你按自己的策略随机化。

**官方客户端**:`pip install pokerai-bet`(Python)· `npm install @pokerai/client`(TS/JS)· `npx @pokerai/mcp`(MCP,给 LLM agent)。均从 [OpenAPI 规范](https://pokerai.bet/openapi.yaml)自动生成、全类型化。

**免费层**:每月 1,000 预解查询 + 25 实时求解,免信用卡 → [拿 Key](https://pokerai.bet/login)。

文档:[中文文档](https://pokerai.bet/docs) · [交互式参考](https://pokerai.bet/reference) · [定价](https://pokerai.bet/zh/pricing)

**禁止**真钱牌桌实时辅助(RTA);面向陪练、教学、复盘、学习与研究。见[条款](https://pokerai.bet/zh/terms)。

</details>
