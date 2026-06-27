# IU-PILOT-001 · 开发期状态标识
## 任务卡（IU Task Card）v0.1

**所属阶段：** Protocol Pilot / 协议试运行  
**优先级：** P0  
**任务类型：** T2 交互状态任务 + T6 平台与执行纪律任务  
**执行角色：** Builder Agent（Manus）  
**当前状态：** Approved  
**目标项目：** 已在 GitHub 建立的 Inner Universe 项目控制仓库  
**预估目标：** 验证 Builder → Supervisor → Verifier 三角色闭环是否能在不需要创始人介入微调的情况下稳定运行。

---

## 一、目标

让开发期验证者能够在不改变用户主体验的前提下，观察当前 HTML Demo 的真实状态流转。

用户或验证者应能看见一个低对比、非正式产品 UI 的状态标识，显示当前体验状态：

```text
macro
gaze
revealing
mirror
responded
returned
```

并显示：

```text
expressionCommitted: true / false
candidateSignalCount: 0
```

本任务不实现真实候选对象、不实现持久化、不修改心理事件逻辑。

---

## 二、完成定义

在现有 Initial Demo 中：

1. 页面首次打开时，状态标识显示：

```text
state: macro
expressionCommitted: false
candidateSignalCount: 0
```

2. 用户点击琥珀对象并进入凝视后，状态标识依次变化：

```text
gaze
→ revealing
→ mirror
```

3. 用户输入文本并获得镜像回应后，状态标识显示：

```text
state: responded
expressionCommitted: true
```

4. 用户点击“让它沉入其中”并返回宏观后，状态标识显示：

```text
state: returned
expressionCommitted: true
candidateSignalCount: 0
```

5. 已有核心闭环保持可用：

```text
宏观
→ 靠近琥珀
→ 停留
→ 显影
→ 镜像输入
→ 镜像回应
→ 沉入其中
→ 返回宏观
```

---

## 三、范围

### 包含

- 在当前 HTML Demo 中增加一个开发期状态标识；
- 将既有状态机映射为可见文本；
- 在已有“回应成功”节点更新 `expressionCommitted`；
- 提供 `candidateSignalCount: 0` 的只读占位字段；
- 保持 UI 极低对比度，不干扰正式体验；
- 提供 Builder 证据以支持后续 Supervisor 与 Verifier 审查。

### 不包含

- 不新增 localStorage；
- 不保存 PsychologicalEvent；
- 不增加 candidateSignalCount 的计算；
- 不生成候选对象；
- 不新增命名功能；
- 不修改镜像回应规则；
- 不增加第二个心理对象；
- 不迁移框架；
- 不重构 HTML/CSS/JS 结构；
- 不修改已冻结视觉语言。

---

## 四、允许

### 可修改文件

仅允许修改以下一个文件：

```text
inner-universe-prototype-v4.html
```

若仓库中的实际文件名不同，Builder 必须先报告实际文件路径与该任务卡不一致；未经批准不得自行选择其他版本文件。

### 可新增文件

```text
无
```

### 可使用工具

```text
浏览器预览；
浏览器开发者工具；
GitHub / Manus 自带的文件编辑和预览能力。
```

### 可执行命令

```text
无
```

### 可新增状态

允许新增或暴露以下只读开发期字段：

```js
state
expressionCommitted
candidateSignalCount
```

说明：

```text
candidateSignalCount 在本任务中必须恒为 0。
它只能作为调试字段出现，不得触发视觉、流程或候选对象变化。
```

### 可使用视觉资产

```text
无新增视觉资产。
```

---

## 五、约束

### 禁止修改

```text
- 不修改宏观场景布局；
- 不修改 Self；
- 不修改琥珀对象形态、颜色、显影效果；
- 不修改微光位置、样式、触发条件；
- 不修改现有镜像回应逻辑；
- 不修改停留时长；
- 不修改已有状态流转顺序；
- 不修改返回行为；
- 不修改现有文案；
- 不修改项目控制仓库中的 protocol、benchmark、task card 文件。
```

### 禁止新增

```text
- 不新增框架；
- 不新增依赖；
- 不新增 npm / package 配置；
- 不新增后端、数据库、localStorage；
- 不新增多页面；
- 不新增正式产品面板；
- 不新增卡片、侧栏、浮窗、聊天列表；
- 不新增额外心理对象；
- 不新增真实 AI 接口；
- 不新增候选对象逻辑。
```

### 禁止视觉语义

状态标识不得：

```text
- 像 Dashboard；
- 像 HUD；
- 像游戏调试面板；
- 像任务进度；
- 像完成奖励；
- 占据视觉中心；
- 使用明亮 RGB、强边框、卡片容器；
- 干扰对象凝视与镜像对话。
```

### 允许的视觉表现

状态标识必须：

```text
- 位于左上或右上角；
- 低对比度；
- 小字号；
- 使用低饱和灰金 / 灰紫 / 灰蓝；
- 可使用等宽字体；
- 透明度低；
- 仅作为开发期辅助信息；
- 不影响点击与输入。
```

### 禁止语言类型

状态标识不得出现：

```text
“完成”
“解锁”
“疗愈进度”
“分析结果”
“诊断”
“心理评分”
“任务”
```

---

## 六、实现假设

### 已知前提

```text
- 当前 HTML Demo 已存在状态机；
- 当前状态至少包括 macro / gaze / revealing / mirror / responded / returned；
- 当前已有“让它沉入其中”的返回动作；
- 当前 Demo 已可完整走通基础闭环。
```

### 不确定点

```text
- GitHub 仓库中的当前 HTML 文件是否命名为 inner-universe-prototype-v4.html；
- 当前状态机变量是否直接暴露或需要增加只读映射；
- Manus 是否能提供浏览器预览截图与变更 diff。
```

### 不确定点处理

若任一不确定点无法确认：

```text
停止。
不要扫描仓库。
不要自行查找多个 HTML 版本。
不要选择“最像的文件”修改。
输出 BLOCKED，并说明最小需要的确认信息。
```

---

## 七、验收标准

### A. 运行检验

必须满足：

```text
A1 页面首次打开时状态标识显示 macro；
A2 点击琥珀后可显示 gaze；
A3 停留显影时可显示 revealing；
A4 光膜出现并可输入时显示 mirror；
A5 提交回应后显示 responded；
A6 点击“让它沉入其中”后显示 returned；
A7 expressionCommitted 只在成功回应后从 false 变为 true；
A8 candidateSignalCount 始终显示 0；
A9 状态标识不会阻挡对象点击、输入框或按钮；
A10 页面无新增控制台错误。
```

### B. 约束检验

必须满足：

```text
B1 仅修改授权 HTML 文件；
B2 未新增文件；
B3 未新增依赖；
B4 未执行命令；
B5 未改动视觉主场景；
B6 未改变既有状态机顺序；
B7 未引入任何持久化或候选对象逻辑。
```

### C. 语义检验

必须满足：

```text
C1 状态标识明显是开发期辅助，而非正式产品 UI；
C2 它不抢占 Self、琥珀、镜像光膜或微光；
C3 它不使产品变成 Dashboard；
C4 它不改变“未知、克制、停留”的体验；
C5 用户不应把它理解为心理进度或完成程度。
```

### D. 回归检验

必须满足：

```text
D1 初始闭环仍完整可走通；
D2 Escape 或现有返回动作仍可用；
D3 琥珀显影仍正常；
D4 镜像回应仍正常；
D5 返回宏观后微光仍正常；
D6 刷新页面仍能正常重新开始当前 Demo。
```

---

## 八、验证路径

### 前置状态

```text
打开当前 Initial Demo。
浏览器刷新一次。
不清空任何已有内容，除非当前 Demo 本身要求首次进入。
```

### 操作步骤

1. 打开页面；
2. 观察状态标识；
3. 点击琥珀对象；
4. 等待进入凝视；
5. 等待显影；
6. 等待镜像光膜；
7. 输入至少 3 个字符；
8. 点击“回应”；
9. 观察状态；
10. 点击“让它沉入其中”；
11. 观察返回宏观后的状态与微光；
12. 使用 Escape 或现有返回机制，确认没有死路；
13. 刷新页面，确认页面仍能从初始状态正常使用。

### 预期结果

```text
步骤 1：state = macro
步骤 4：state = gaze
步骤 5：state = revealing
步骤 6：state = mirror
步骤 8：state = responded，expressionCommitted = true
步骤 10：state = returned，微光仍存在
所有阶段：candidateSignalCount = 0
```

### 失败判定

任一出现即 Fail：

```text
- 状态标识不随真实流程变化；
- 响应后仍显示 expressionCommitted: false；
- candidateSignalCount 非 0；
- 原有闭环无法走通；
- 新标识遮挡输入或点击；
- 新标识变成显眼正式 UI；
- Builder 修改了授权之外的文件；
- Builder 使用未经允许的命令；
- Builder 仅声称完成但无截图、diff 或预览证据。
```

---

## 九、交付证据

Builder 必须提交以下材料：

```text
1. 修改文件清单；
2. 精确 diff；
3. 未授权修改声明；
4. 未执行命令声明；
5. 至少 6 张截图，分别覆盖：
   - macro
   - gaze
   - revealing
   - mirror
   - responded
   - returned
6. 可访问预览链接或可运行产物；
7. 自测步骤及结果；
8. 已知限制；
9. 任务状态只能写：EVIDENCE SUBMITTED。
```

Builder 不得使用以下结论：

```text
PASS
VERIFIED
FULLY COMPLETE
PRODUCTION READY
```

---

## 十、失败处理

### 无法定位目标文件

```text
输出：
STATUS: BLOCKED
REASON: Authorized target file cannot be confirmed.
WHAT I VERIFIED:
WHAT I DID NOT CHANGE:
MINIMUM DECISION NEEDED:
```

不得扫描整个仓库寻找候选文件。

### 需要修改未授权文件

```text
停止。
输出：
STATUS: BLOCKED
REASON: Task requires modification outside authorized file scope.
```

### 需要新增依赖、框架或命令

```text
停止。
不得自行执行。
```

### 原有闭环被破坏

```text
停止。
保留当前 diff。
明确标记回归项。
不得继续“顺手修复”。
```

### 视觉语义不确定

```text
停止。
输出截图。
将问题标记为:
NEEDS FOUNDER REVIEW
```

---

## 十一、停止条件

Builder 达成以下条件后必须停止：

```text
- 一个低对比状态标识存在；
- 它真实映射六个状态；
- expressionCommitted 在回应后为 true；
- candidateSignalCount 恒为 0；
- 原有 Initial Demo 主路径仍完整；
- 提交完整证据。
```

明确禁止继续：

```text
- 不做 localStorage；
- 不做事件保存；
- 不做候选对象；
- 不做命名；
- 不做视觉升级；
- 不做镜像文案重写；
- 不做第二个对象；
- 不做项目重构；
- 不做性能优化；
- 不做 GitHub 工作流配置。
```

---

## 十二、Builder 启动提示

将以下内容作为 Manus Builder 的首段指令，并同时提供本任务卡。

```text
You are the Builder Agent for Inner Universe.

Your only responsibility is to complete task IU-PILOT-001 exactly as specified in the attached task card.

Read only:
1. This task card;
2. The explicitly authorized target file;
3. The applicable verification section inside this task card.

Do not scan the repository.
Do not inspect parent directories.
Do not modify any file other than the authorized HTML file.
Do not create files.
Do not use terminal commands.
Do not install dependencies.
Do not refactor.
Do not add any feature not written in the task card.
Do not claim PASS or VERIFIED.

When finished, submit only:
- modified file list;
- exact diff;
- preview link or runnable artifact;
- six state screenshots;
- self-test steps;
- known limitations;
- STATUS: EVIDENCE SUBMITTED.

If any authorization or target-file detail is uncertain, stop and report BLOCKED. Do not guess.
```

---

## 十三、Supervisor 交接包

Supervisor 只接收：

```text
- 本任务卡；
- Builder 的修改文件清单；
- Builder diff；
- Builder 命令轨迹或“未执行命令”声明；
- Builder 截图与预览链接；
- Builder Evidence Submitted。
```

Supervisor 不得阅读 Builder 的长篇解释，不得修改产物。

---

## 十四、Verifier 交接包

Verifier 只接收：

```text
- 本任务卡；
- 可访问预览链接或 HTML 产物；
- 六张关键状态截图；
- diff；
- P1、A1–A8、R1–R7 的相关 benchmark 摘要。
```

Verifier 不得根据 Builder 自述判定完成。

---

## 十五、任务结束状态

待 Supervisor 与 Verifier 完成后填写：

```text
SUPERVISION RESULT:
-

VERIFICATION RESULT:
-

HARD FAILURES:
-

FINAL DECISION:
PASS / REWORK / REDESIGN / BLOCKED

FAILURE LEDGER ENTRY:
-

NEXT ACTION:
-
```
