# <span data-name="cow" data-type="emoji">🐮</span> 小瘦金牛牛解密

佛系消消消解密工具

智能识别棋盘截图，自动求解「找牛」类逻辑谜题的工具。支持单牛/双牛两种模式，上传截图即可秒得答案。

---

## <span data-name="sparkles" data-type="emoji">✨</span> 功能特性

<table style="width: 713px">
<colgroup><col style="246px"><col style="467px"></colgroup><tbody><tr><td colspan="1" rowspan="1" colwidth="246"><p>功能</p></td><td colspan="1" rowspan="1" colwidth="467"><p>说明</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="camera" data-type="emoji">📷</span> 截图识别</p></td><td colspan="1" rowspan="1" colwidth="467"><p>上传棋盘截图，自动识别颜色矩阵</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="scissors" data-type="emoji">✂</span> 裁剪框选</p></td><td colspan="1" rowspan="1" colwidth="467"><p>使用 Cropper.js 精准框选棋盘区域</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="high_voltage" data-type="emoji">⚡</span> 快速模式</p></td><td colspan="1" rowspan="1" colwidth="467"><p>无需裁剪，直接上传求解</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="blue_circle" data-type="emoji">🔵</span> 单牛模式</p></td><td colspan="1" rowspan="1" colwidth="467"><p>N×N 棋盘，每行/列/颜色各 1 头，互不相邻</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="green_circle" data-type="emoji">🟢</span> 双牛模式</p></td><td colspan="1" rowspan="1" colwidth="467"><p>N×N 棋盘，每行/列/颜色各 2 头，互不相邻</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="bullseye" data-type="emoji">🎯</span> 结果标注</p></td><td colspan="1" rowspan="1" colwidth="467"><p>求解结果以圆圈直接标注在棋盘 Canvas 上</p></td></tr><tr><td colspan="1" rowspan="1" colwidth="246"><p><span data-name="android" data-type="emoji">📱</span> 移动友好</p></td><td colspan="1" rowspan="1" colwidth="467"><p>响应式设计，手机端也可使用</p></td></tr></tbody>
</table>

---

## <span data-name="computer" data-type="emoji">💻</span> 使用步骤

1. **选择模式** — 打开 `https://niu.yzz.me/`，选择「单牛」或「双牛」模式

2. **选择上传方式** — 裁剪后求解（精准）或直接上传（快速）

3. **上传截图** — 拖拽或点击上传游戏棋盘截图

4. **设置 N 值** — 输入网格数（5-30），或使用快捷按钮 10/11/12

5. **查看结果** — 系统自动识别并求解，结果标注在棋盘上

---

## <span data-name="brain" data-type="emoji">🧠</span> 算法说明

### 单牛模式（N 头牛）

约束条件：

- 每行恰好 1 头牛

- 每列恰好 1 头牛

- 每种颜色恰好 1 头牛

- 任意两头牛不能相邻（含对角，即 3×3 范围内不能有其他牛）

求解策略：按行递归，每行尝试所有列，满足约束则继续下一行。

### 双牛模式（2N 头牛）

约束条件：

- 每行恰好 2 头牛

- 每列恰好 2 头牛

- 每种颜色恰好 2 头牛

- 任意两头牛不能相邻（含对角）

求解策略：逐行逐列搜索，使用行/列/颜色计数器剪枝，大幅减少搜索空间。

---

## <span data-name="warning" data-type="emoji">⚠</span> 注意事项

- N 值范围为 5-30，超出范围会报错

- 双牛模式 N 较大时（≥18）求解时间可能较长，PHP 超时时间已设为 120 秒

- 截图需尽量清晰，棋盘区域完整，颜色区分明显

- 裁剪时尽量使棋盘区域占满正方形框选区域，识别更精准

- 本工具仅供学习交流使用

---

## <span data-name="page_facing_up" data-type="emoji">📄</span> 许可

本工具为个人学习项目，仅供交流使用。
