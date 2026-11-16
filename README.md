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


## 独立皮肤模型零件（V0.6）

男性人体表面已改用独立分割的 `skin-segmented.glb`，包含 **256 个分别命名的皮肤网格零件**。点击人体时，射线拾取直接命中一个实际 GLB mesh，并只高亮该 mesh；不再根据点击坐标猜测身体区域，也不再生成圆形覆盖色块。右侧粗粒度身体区域仅根据零件名称进行分类，供后续症状流程使用。

- 模型文件：`models/skin-segmented.glb`（约 0.77 MB）。
- 来源：[SeemaBansal1/3d-human-body-anatomy](https://github.com/SeemaBansal1/3d-human-body-anatomy)，Z-Anatomy / BodyParts3D 衍生皮肤分区。
- 压缩：Draco；浏览器通过 Three.js DRACOLoader 加载。
- 署名及许可：见 [ATTRIBUTION-SEGMENTED-SKIN.md](./ATTRIBUTION-SEGMENTED-SKIN.md)。该模型衍生数据采用 CC BY-SA 4.0，必须保留署名并遵守相同方式共享要求。

**当前范围限制：** 256 个独立皮肤网格目前用于成年男性模型。女性模型仍使用原有整体皮肤网格，女性独立表面分区尚未接入；界面会明确提示，不会假装已完成。肌肉、骨骼、器官等内部结构继续使用 Open Anatomy 3D 的独立命名网格，关闭皮肤图层后可逐个选择。

