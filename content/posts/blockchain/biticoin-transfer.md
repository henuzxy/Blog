# 当你向一个比特币地址转账，整个过程发生了什么

## 流程图

![image](https://mermaid.ink/img/pako:eNqdWFtP21Yc_ypRqkpMCpEviXN5QGq4PKHuAbSnvJzYJ4kVx85sp4UhpIwWFVDahkFZN0BAV_pCuUxDtDQt-TCLnfC0r7Dj2E7s49jJdiJFsc_vf_v9L-fASpiVOBhOhxX4YxWKLJzhQUEG5awYQqsCZJVn-QoQ1RDgOBkqyqMQUELawZV2WHvkBZV5Eco9SOeopX069YNkBpCMr6nMwJQF6vswOTll_06H9ONb_eVFZ_9CP35hwv_5Wu9--9i9_nD_Yvv-3SF6NG11r287u0f6RqP95b3-dqfdOtF_vtRubzrnd1rjpdvG5NSUGU1au23pv5x3L09NKRNm7iE_nI7s3mgbVxgQ15cJ0JcZQ1_fsOWdvrXVR-i7d9q6_fvP4-ECoXbzVR_S_nx-X9vUXu-Zbwwums8RQfrelVb_orXOfHR0W_vdk3r36pn-5lp8LKHC0Q9PtcumvnlnJWJnQ_tc12pfDfL3r1EcaAt9dz5-0Bobnd-f9wH6xl63tq4fbFo2D3_tvjszQ-80d_TDo79raxhHNpGNun78Sd_c0errwx3GOB8GcujT_6jpR6d9x9rNU-31lkXV20utYXiu__UmwJ9tbf2m3dzrbq111m77eTajwsrBnemeZacpxEHn5KJ78R7xp13UUUq0xit9_xqF0P72Gypqlzpn4dhx6Ae1bmvbymt9XWucGa7Y_YEybXKcU1mzV9BLU7-Jsa1kxXAkXIZyGfAcmhMrht1sWC3CMsyG0-gnB_OgKqjZcMSx9QOQeZAToGJgVkxfs-EcYEsFWaqKnCn6tMir0BI09isyXwby8rQkSLKJeDA7PTs9N-fAKJCVRA5D5dHinJpUiMaJG1RUhIkkEQmRBPEwEkoxUSoRixOpJEGnHn7ndSIjyRyUMXkqhhQwhnzSV77v4FANTF8BHY1TqRhJJphYwqXA9n2ofHK0A1YAi3BJdXJE0iRNEMMcxZEEWhQ5xCMMKBdyE6lonLAWiVj1fXI6KKB2cdqje8tlz-2QexdVopgpFYILZADw1EauxytpbafoBDGT8WxT1jZAy2UdyLL0tAgBFxhBXhLVOVDmhWUTkc2iqGSYq7JFiM5AxXiOhJ5AmQMiiISMbhEw8QX-J6vDSKay5KQP5KCQwVrpAUwaHwdMRAd7AE297V6ofkSwQlVBmQ9g0kY41XgIs-bDPC-WgpPOqwL0zzrkCnB-vMgBq0oup3qtG09FGYohmSRFxehICD0mEkycZmiSShr9lIimCDLFEIlkjHb1k6nOn8nePtYaOQF5iWPm3XVfkOGys275gggEfwLM_cXA1jBLQ1pC3gYO0T5u6JD730z11I5gQpCkygiIKKnQ45m3sHowd6CoQOOAwzCjU8M_ASoviV6bDMMMR2JmY8bHNYPM2_Tjajnn0oifeGhYefWhuQomSIIyzir0RcXjkRARjaVcRSmoC8NkRxigBkTFXIeBCpSSN_44HcvnWBzmDj4JUgTHYRiD83m-UFQDXLNxY0BmgFwKSKEN-76qKjwHx0BOCzxbMi4o7nOPJhkaTzhcHI8aB9hNUC7PJvJ5B7Ig887TQzB4woYBJ4lDVAUicQ8xHCvzqjeKfD6JFg5zVyN0JVfiwDI2yNyI3hAISAFEB6iMURSPU2jhIHzWeVCsABTFQPldcfK8ICwuVyDhNwhtAOl3xNkAajAfaSI2-hZpy9EDOZIayPle_my5mEMuwYxvLz6Qm_wP5hjHDXN8YwmHk8mkrzVDbDUrrqI_JEBVlRaWRTacVuUqjISrFQ6o9j8dwuk8EJT-21mOR4em9XL1XxZ42BY?type=png)



## 创建交易

在你输入目标地址，以及转账金额和矿工费用后。你的比特币钱包会生成一个结构体记录交易的信息。

比特币交易的结构体由以下几个部分组成：

1. 版本号（Version）：交易数据格式的版本。
2. 输入计数（Input Counter）：指明多少个输入被包括在这次交易中。
3. 输入（Inputs）：每一个输入包含以下内容：
   - 交易的引用（Transaction Reference）：这是一个对之前发生的交易的引用，说明了这些比特币的来源。
   - 输出索引（Output Index）：标识在引用的交易中的哪一个输出。这是因为每个比特币交易可以有多个输出。
   - 解锁脚本大小（Unlocking Script Size）：解锁脚本（通常包含签名和公钥）的大小。
   - 解锁脚本（Unlocking Script）：包含用于解锁输入的数据。通常是包含了签名和公钥的脚本。
   - 序列号（Sequence）：目前大部分情况下默认为0xFFFFFFFF，主要用于标示交易的可替代性。
4. 输出计数（Output Counter）：指明多少个输出被包括在这次交易中。
5. 输出（Outputs）：每一个输出包含以下内容：
   - 数额（Value）：要发送的比特币的数量，单位是Satoshi（比特币的最小单位，1比特币=1亿Satoshi）。
   - 锁定脚本大小（Locking Script Size）：锁定脚本（通常包含接收方的公钥哈希）的大小。
   - 锁定脚本（Locking Script）：包含用于锁定输出的数据。通常是包含了接收方的公钥哈希的脚本。
6. 锁定时间（Locktime）：交易何时能被添加到区块链的时间约束。如果设置为0，表示没有约束。

## 签名交易

你的比特币钱包会使用你的私钥对整个交易进行签名。签名的目的是为了验证这笔交易是由你发起的，并且交易签名后，不可被篡改。签名的目的是保证交易的完整性和防止双花，只有拥有正确的私钥才能创建有效的签名，而其他节点可以用公钥来验证这个签名。

## 广播交易

当交易信息生成后，比特币钱包会把这笔签名后的交易发送到比特币网络，也就是会向连接的所有其他节点广播这笔交易，其他节点检查交易信息正确后也会继续广播给他们所连接的节点。于是这笔交易就在比特币网络中传播开。

比特币网络使用的是P2P 协议。在比特币网络中，新的节点（包括矿工节点）通常通过以下几种方式连接到其他节点：

1. **固定种子节点（Hardcoded Seed Nodes）**: 在比特币软件中，开发者会预先设定一些稳定可靠的节点地址作为种子节点。新的节点在启动时，会尝试连接这些种子节点，然后通过这些种子节点获取更多的节点信息。
2. **DNS种子（DNS Seeds）**: 除了预设的固定种子节点，比特币软件也设定了一些DNS种子。这些DNS种子是一些域名，当新的节点向这些域名发送请求时，DNS服务器会返回一些活跃节点的IP地址。
3. **地址广播（Address Broadcasting）**: 当一个节点连接到网络中，它会从已经连接的节点处获取更多节点的信息。每个节点都会周期性地广播它知道的其他节点的信息。
4. **手动添加（Manual Addition）**: 用户也可以手动添加节点的信息，例如，如果用户知道某个节点是稳定可靠的，他们可以直接把这个节点的信息添加到自己的比特币客户端中。

## 矿工确认交易

矿工节点在收到一笔交易时，会先放入一个mempool(交易池)。矿工节点会优先取交易费比较高的交易打包到一个新的区块。这个区块包含上一个区块的哈希值，时间戳和其他信息如下

```cpp
int32_t nVersion;
uint256 hashPrevBlock;
uint256 hashMerkleRoot;
uint32_t nTime;
uint32_t nBits;
uint32_t nNonce;//初始值为0，不断改变该值来重新进行哈希计算，知道求的目标的哈希值。
```

### POW 证明

工作量证明采取搜索一 个数，使得被哈希时（如使用 SHA-256）得到的哈希值以数个 0 比特开始。平均所需工 作量将随所需 0 比 特呈指数级增长而验证却只需执行一次哈希。

矿工在不断的调整nNonce,当哈希值符合后，会把这个新区块广播给其他节点，于是这笔交易就在比特币网络中传播开。

## 接收者接接收比特币

比特币钱包会检查区块链的新区块，看是否有新的交易发送到你的地址，如果有，那么钱包会把更新你的余额。



## 常见问题

1. 一次转账一般要多久？

   在比特币网络中，一个交易被确认的次数通常与它在区块链中的深度有关，也就是说，被多少个新的区块覆盖。一旦一个交易被打包进一个区块并且被添加到区块链中，我们就说这个交易被确认了一次。

   但是，只有一次确认并不能完全保证这个交易是最终被确认的，因为在比特币网络中可能会出现短暂的分叉（fork），也就是存在两个或更多个有效的区块被同时挖出的情况。在这种情况下，网络需要等待更多的区块被添加，看哪个分叉更长（也就是有更多的工作量证明），然后选择它作为主链。

   基于安全考虑，一般认为你交易的那个区块后面再添加6个新的区块，所以总共是7个区块，大概需要70分钟。

2. 比特币交易费如果输入一个很低的费用，btc会不会丢失？

   如果你设定了一个非常低的交易费用，那么在比特币网络拥堵的情况下，你的交易可能会等待很长时间才能得到矿工的确认，或者可能甚至不会被确认。

   因为交易是矿工放入交易池，如果因为不断有新的交易导致这笔交易一直无法被确认，直到被所有矿工节点从交易池中删除，可以认为交易被取消，但也有可能经过一个很长时间的滞留在某个网络不拥堵的时候该交易被确认（目前比特币网络还没有交易过期的逻辑）但是你的btc不会丢失，没有确认时依然留在你的钱包，如果被确认了也是会转到你的目标钱包。

   



