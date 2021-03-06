---
title: blockchain入门
author: 菲尼莫斯
date: 2018-12-20
tags:
categories:
- 区块链
---

# blockchain入门

by 菲尼莫斯 2018年12月20日

---

>极客们彼此创造深奥晦涩的词汇来建立行业壁垒,把自己弄得云里雾里,失去了与正常人沟通的能力。普通大众则马不停蹄地参加各种论坛沙龙,如饥似渴地汲取新知,唯恐坠入智能时代的底层。

>没有上帝,没有国王,也没有政府和大公司这样的权威居高临下或者中心操控,而世界仍然在运行,而且更重要的是,革命正在发生。

>许多人将区块链视为一个巨大的分布式记账体系,但区块链显然要远远超过记账的认证功能。

>区块链说到底更是一种观念,用技术设计取代权威控制和情感信任,以此建立一种网络结构,所有人都可以参与成为无数节点之一,进行认证、确权、交易、追溯和调整等一系列动作,它公开透明,成本低、速度快、分布广,没有权威可以篡改伪造和取缔记录。

>与其相信人,不如相信技术。

>这样一个建立在运算能力和技术架构上的网络文明社会基础设施将是多么不同。尽管它毫无情怀和冰冷冷地运作,但从根本上摈弃了狂热理想的驱使、自命权威的霸道、垄断财团的曲扭、民粹阴谋的盲动,商业诈骗和情感敲诈也会随之水落石出。

>一个经典的例子是两个人来分一个蛋糕,如果都想拿到较大的一块,在没有第三方的前提
下,该怎么指定规则才公平?
最简单的一个方案是负责切蛋糕的人后选。

# 分布式算法

* FLP不可能原理：在异步通信场景，即使只有一个进程失败，也没有任何算法能保证非失败进程达到一致性

* 拜占庭问题： 总节点：N，问题节点：f，当n>=3f+1时系统可用

## 分布式系统标准

* 可终止性(Termination):一致的结果在有限时间内能完成;

* 共识性(Consensus):不同节点最终完成决策的结果应该相同;

* 合法性(Validity):决策的结果必须是其它进程提出的提案。

### ACID一致性要求

* Atomicity:每次操作是原子的,要么成功,要么不执行;

* Consistency:数据库的状态是一致的,无中间状态;

* Isolation:各种操作彼此互相不影响;

* Durability:状态的改变是持久的,不会失效。

## 分布式的CAP原理

* 一致性(Consistency):任何操作应该都是原子的,发生在后面的事件能看到前面事件发生导致的结果,注意这里指的是强一致性;

* 可用性(Availablity):在有限时间内,任何非失败节点都能应答请求;

* 分区容忍性(Partition):网络可能发生分区,即节点之间的通信不可保障。

## PBFT算法

n个节点，共识需要至少(2n+1)/3个

1. 请求生成区块（requsest）

选出Leader节点

2. 预准备阶段（pre-prepare）

所有节点把自身收集到的交易向全网广播，Leader节点将这些交易排序后存入列表，并将列表向全网广播

3. 准备阶段（prepare）

每个节点按照Leader的列表模拟执行这些交易，若所有交易执行通过，计算出新区快的哈希摘要向全网广播

4. 提交阶段（commit）

如果一个节点收到2f条哈希摘要（f为可容忍的拜占庭节点数），且与自己计算的相等，则向全网广播commit消息

5. 生成完成（reply）

如果一个节点收到2f+1条commit消息，即可将新区块写入本地数据库。

## 无拜占庭节点下的分布式算法

Paxos、Raft算法

# 区块链技术

## 闪电网络

基本原理：将交易转移到链下进行

* RSMC　Recoverable Sequence Maturity Contract：双方通过数字签名修改两人的共同资金分配，达到转账的目的

* HTLC Hashed Timelock Contract：确保使用闪电网络的双方能点对点链接的通道




