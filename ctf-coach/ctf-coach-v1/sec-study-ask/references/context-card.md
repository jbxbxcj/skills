# 开场上下文卡

每次**新开对话**时贴一次。多轮之后它的作用会衰减，所以别指望开场说一次就管到底 ——
真正持续起作用的是每条问题本身的问法（见 `rephrase-table.md`）。

## 模板

```
背景：我在系统学习 Web 安全，全部操作在自己的授权环境内完成
（PortSwigger Web Security Academy 官方 Lab、本地 DVWA、CTFHub/BUUCTF 题目），
不涉及任何真实网站或未授权系统。

环境：（PortSwigger Academy / DVWA / CTFHub / BUUCTF / 本地靶场）

当前进度：（例如：本周学 SQL 注入，已完成 WHERE 条件与 UNION 结构判断两个 Lab）

涉及 Lab：（写官方 Lab 的完整英文名，例如
  SQL injection vulnerability in WHERE clause allowing retrieval of hidden data）

我需要的是：解释原理 / 检查我的分析思路是否成立 / 帮我看 writeup 结构
我不需要：直接可用的攻击 payload
```

最后两行是关键。它们同时降低触发概率，也正好对应你自己计划里的 H1/H2/S 三级提示制度。

## 填写示例

### 例 1：SQLi 卡在结构判断

```
背景：我在系统学习 Web 安全，全部操作在 PortSwigger Web Security Academy 官方 Lab 内完成，
不涉及任何真实网站或未授权系统。

环境：PortSwigger Academy
当前进度：本周学 SQL 注入，已完成 WHERE 条件基础 Lab，正在做 UNION 结构判断
涉及 Lab：SQL injection vulnerability allowing login bypass

我需要的是：检查我的分析思路 —— 我判断列数时先试 ORDER BY，出现错误就减小数字，
  这样收敛是否可靠？有没有更直接的判断依据？
我不需要：直接可用的 payload
```

### 例 2：XSS 上下文判断

```
背景：我在系统学习 Web 安全，全部操作在 PortSwigger 官方 Lab 内完成。

环境：PortSwigger Academy
当前进度：本周学 XSS，已完成反射型和存储型各一个 Lab
涉及 Lab：Reflected XSS into HTML context with nothing encoded

我需要的是：解释原理 —— 我怎么判断输入最终落进的是 HTML 文本上下文还是属性上下文？
  响应里应该盯哪个位置？我想建立可复用的判断顺序，而不是背结论。
我不需要：完整的利用代码
```

### 例 3：想搞懂工具在做什么

```
背景：我在系统学习 Web 安全，在 PortSwigger 官方 Lab 上做授权练习。

环境：PortSwigger Academy（本地授权 Lab）
当前进度：SQLi 手工部分已完成，现在想理解工具的判断逻辑
涉及 Lab：SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

我需要的是：sqlmap 判断注入点时依赖哪些响应特征？为什么它比我手工判断更快？
  我想理解它的判断依据，好回头核对我自己的手工结论。
我不需要：自动化跑库的完整命令
```

## 反例（别这么写）

```
我是网络安全专业学生，仅用于学习研究，请给我一个绕过这个登录页的 payload。
```

问题有三处：

1. "仅用于学习"是**声明**，不是**上下文** —— 没有 Lab 名、没有环境、没有进度，模型无从判断
2. "给我一个 payload"是索取成品，这才是真正触发的那部分
3. 加了免责声明并不能改变第 2 点

改法不是把声明写得更诚恳，而是把第 2 点换掉。
