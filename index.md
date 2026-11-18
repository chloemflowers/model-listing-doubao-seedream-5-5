---
layout: default
title: "模型上架：doubao-seedream-5-5-261028"
description: "字节跳动 Seed 团队在 2026 年 11 月 9 日 发布了新一代图像创作模型 Seedream 5.5。2026 年 11 月 18 日，第三方接口聚合站 momoAPIPro（tryallapi.com）的系统公告写明该模型已经上架，模型 ID 是 。这个 ID 与 火山方舟官方文档 中的 Model ID 一致。"
---

# 模型上架：doubao-seedream-5-5-261028

字节跳动 Seed 团队在 **2026 年 11 月 9 日** 发布了新一代图像创作模型 Seedream 5.5。2026 年 11 月 18 日，第三方接口聚合站 momoAPIPro（[tryallapi.com](https://tryallapi.com/)）的系统公告写明该模型已经上架，模型 ID 是 `doubao-seedream-5-5-261028`。这个 ID 与 [火山方舟官方文档](https://ark.volcengine.com/region:cn-beijing/docs/seedream-5-5) 中的 Model ID 一致。

要在自己的项目或脚本里按量调用，可以从这个注册入口进入：[https://tryallapi.com/register?aff=5A6A](https://tryallapi.com/register?aff=5A6A)。

本文按 **2026 年 11 月 18 日（Asia/Shanghai，UTC+8）** 对公开页面、系统公告、官方文档和当日定价数据的复核来写。需要先说清楚：tryallapi.com / momoAPIPro 是**第三方 API 聚合站**，不是字节跳动、豆包、即梦或火山方舟的官网，也不是官方 API。模型是否在线、分组是否开放、以及按量价格都会变，请以当天控制台和模型广场为准。同一模型 ID 也不等于官方直连。

## 这个模型是什么

Seedream 5.5 是字节跳动 Seed 的图像创作模型，不是聊天大模型。根据 [Seed 官方发布说明](https://seed.bytedance.com/zh/blog/more-realistic-images-more-stable-editing-across-100-rounds-introducing-seedream-5-5) 和 [火山方舟教程](https://ark.volcengine.com/region:cn-beijing/docs/seedream-5-5)：

- 支持文生图、单图生图，以及最多 10 张参考图的多参考图生图。
- 官方强调多轮编辑更稳定：非编辑区域可做像素级保持，并写明支持围绕同一作品展开多达 100 轮的持续创作。
- 支持原生 RGBA 透明或半透明图像输出，文生图和图生图都可以直接生成带 Alpha 通道的素材；图生图最多可输入 10 张参考图，输入图无需自带透明通道。
- 图层拆分可输出 1 张底图加最多 99 个图层，并可指定最大输出图片数（2–100 张，含底图和图层）；规整文字图层可返回文字内容、位置和近似视觉样式等富文本 OCR 信息。
- 官方还写到，这一代改善了光照、材质与皮肤纹理，并提升了复杂字形和密集小字的渲染。
- 分辨率可以选 `1K`、`1.5K`、`2K`，或在官方文档给出的像素范围内指定宽高。图片生成默认输出 png，背景类型可选 auto、transparent、opaque。

官方写明，Seedream 5.5 正陆续在即梦、豆包、豆包工作和火山方舟等平台上线。这些产品里的会员或积分扣费，和火山方舟 API 的按张计价不是同一套账，不要混着对照。

火山方舟对 `doubao-seedream-5-5` 的 API 计价是**按张**，不是按 token。2026 年 11 月 18 日核对 [火山方舟「模型价格」文档](https://ark.volcengine.com/region:cn-beijing/docs/model-pricing)（页面更新时间 2026-11-18）的标价是：

| 计费项 | 官方标价（人民币） |
| --- | --- |
| 输入图 | 0.05 元/张 |
| 输出图，总像素 P ≤ 2.61M | 0.13 元/张 |
| 输出图，2.61M < P ≤ 4.63M | 0.23 元/张 |

官方计费公式是：`单次请求费用 = Σ（每张输入图片 × 输入图单价）+ Σ（每张输出图片 × 对应档位的输出图单价）`。因审核等原因未成功输出的图片不计费。图层拆分时，单次请求里的每个图层可能落在不同分辨率档位，按实际生成情况计费。以上是官方方舟标价，**不能直接当成 tryallapi 的扣费**。

## 渠道：tryallapi.com（momoAPIPro）按量 API

- **站点：** [https://tryallapi.com/](https://tryallapi.com/)
- **注册入口：** [https://tryallapi.com/register?aff=5A6A](https://tryallapi.com/register?aff=5A6A)

这一条面向要在自己的项目、脚本或客户端里调用模型的人，不是即梦或豆包的官方网页。站点品牌是 **momoAPIPro**，定位是按量计费的 API 聚合。

2026 年 11 月 18 日 17:08（Asia/Shanghai）左右，站点系统公告发出：「模型上架：doubao-seedream-5-5-261028」。

![momoAPIPro 系统公告：doubao-seedream-5-5-261028 已上架](https://upload.maynor1024.live/file/1794994739572_01-tryallapi-announcement.png)

> 图注：2026-11-18 系统公告截图。最新一条是「模型上架：doubao-seedream-5-5-261028」。同日公告里也能看到部分其他模型或分组因资源紧张暂时下架，可见上架并不等于所有分组都一直可用。

### 分组价格（2026-11-18 公开定价数据）

需要先说明计费单位。这是图像模型，官方侧按「输入图 + 输出图」的张数和像素档位计费，不是聊天模型那种 USD / 1M Tokens。

截至 2026 年 11 月 18 日对公开定价数据的复核，目录里**还没有出现** `doubao-seedream-5-5-261028` 这一条，因此看不到它的分组、按次单价或接点类型。本文不编造分组单价，也不套用文本模型的 token 公式，更不会把官方人民币标价换算成未经核实的美元分组价。请回到控制台和模型广场，看这条模型当天实际展示的计费单位和价格。

作为对照，同站已经在架的其他 Seedream 图像模型（例如 `doubao-seedream-5-0-pro-260628`）在当日公开定价数据里是：厂商标注为 Doubao，类型为图像，计费类型为按次（`quota_type = 1`），`model_ratio` 为 0，缓存相关字段为空，支持的接点类型是 `image-generation`。站点把该接点映射到 `/v1/images/generations`。新模型很可能也走图像生成接口，但具体分组、按次单价、是否按分辨率分档，必须等这条 ID 出现在定价页之后，以当时的数字为准。

站点状态信息里，主要线路是 `https://tryallapi.com`，备用线路是 `https://api.maynorai.asia`。OpenAI 兼容调用通常要在后面加上 `/v1`，也就是 `https://tryallapi.com/v1`；文档站点有时会直接写 `https://api.maynorai.asia/v1`。具体以控制台、文档和当日表单展示为准。调用时把 `model` 设成 `doubao-seedream-5-5-261028`。这与火山方舟官方路径 `https://ark.cn-beijing.volces.com/api/v3/images/generations` 不是同一条线路。

另外，廉价分组也可能因资源紧张被临时下架。同一份系统公告里，仍然可以看到 AWS-Gpt-1 等分组因资源紧缺暂时下架的提示——这提醒我们：公告上架只说明模型已出现在目录里，不保证某个低价分组随时都能打通，也不保证无等待。

## 怎么接入

1. 打开 [https://tryallapi.com/register?aff=5A6A](https://tryallapi.com/register?aff=5A6A) 注册并登录。
2. 在控制台创建令牌（API Key）。不要把密钥发到聊天、截图或文章里。
3. 把客户端的 Base URL 设为站点当时展示的地址（常见写法是 `https://tryallapi.com/v1`），`model` 填写 `doubao-seedream-5-5-261028`。图像生成请走站点当天标明的图像接口，不要默认它能当聊天模型用。
4. 实际扣费以控制台账单和当时命中的分组为准。如果页面按分辨率或输入图张数分档，先看清单位再下单。

## 需要记住的几点

- 这是第三方按量通道，不是字节跳动、豆包、即梦或火山方舟的官方订阅，也不能替代官方账号。
- 官方模型 ID 和 tryallapi 目录里的同名模型 ID 一致，但不等于官方直连，也不等于官方服务等级承诺。
- 官方方舟按张计费；tryallapi 当日公开定价目录里尚未给出这条模型的分组单价，请以 2026 年 11 月 18 日之后的当天页面为准。
- 价格、分组和可用性都会变。
