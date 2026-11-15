# 看诊 1.0 · 智能触控导诊演示

这是从私有开发仓库同步的公开 Web 演示版本，仅用于产品体验和交互评估。

## 在线体验

https://zmc1212.github.io/kanzhen-ai-demo/

## 当前演示功能

- 成年男性 / 女性完整人体模型切换（皮肤表面默认显示）。
- 皮肤、骨骼、肌肉、内脏、血管、神经系统图层切换。
- 真实解剖网格点击拾取、结构名称提示和选中高亮。
- 3D 旋转、缩放、正面 / 背面视角、局部区域聚焦。
- 身体区域选择、症状多选、导诊结果演示。

## 技术与模型

- Three.js 0.171、GLTFLoader、MeshoptDecoder、OrbitControls。
- 3D 模型来自 [MervinR07/open-anatomy-3d](https://github.com/MervinR07/open-anatomy-3d)，固定使用 npm 包版本 0.1.0。
- 模型约 7.6 MB（男性）和 8.1 MB（女性），采用 Meshopt 压缩。
- 模型许可：CC BY 4.0。完整来源和许可说明见 [上游 ATTRIBUTION.md](https://github.com/MervinR07/open-anatomy-3d/blob/main/packages/open-anatomy-3d/ATTRIBUTION.md) 与 [LICENSE-MODELS.md](https://github.com/MervinR07/open-anatomy-3d/blob/main/packages/open-anatomy-3d/LICENSE-MODELS.md)。

### 必须保留的模型署名

> Anatomy: BodyParts3D © The Database Center for Life Science (CC BY 4.0); female organs: Human Reference Atlas 3D Reference Organs, HuBMAP (CC BY 4.0); female body: MakeHuman (CC0). Modified by open-anatomy-3d (https://github.com/MervinR07/open-anatomy-3d), CC BY 4.0.

本演示从 jsDelivr 加载模型文件和结构目录，首次打开需要网络连接。

## 医疗安全说明

这是交互与视觉演示，不是医疗器械、诊断工具或经过验证的分诊系统。症状列表、疾病条目、匹配百分比和科室建议均为演示数据，不得用于真实患者诊疗或急症排除。正式临床试点前必须由医疗专业人员审核、验证分诊规则，并完成隐私、安全、审计及适用监管要求。
