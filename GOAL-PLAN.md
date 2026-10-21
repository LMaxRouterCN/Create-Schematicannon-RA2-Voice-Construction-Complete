# Create Schematicannon: RA2 Voice Construction Complete

将机械动力(Create)蓝图加农炮的"打印完成"音效替换为红警2的 Construction complete 语音.

## 关键决策
- 目标版本: MC 1.20.1, pack_format=15
- 原事件 schematicannon_finish 引用的是 event 类型 minecraft:block.note_block.bell, 若直接覆盖bell会污染全局音符盒音效, 故采用资源包重定义该事件指向自有音频
- sounds.json 条目使用 replace: true, 确保覆盖而非追加(默认false会把语音追加进列表, 与原bell随机二选一播放)
- subtitle 保留 create.subtitle.schematicannon_finish (字幕走Create翻译, 语音为英文EVA)
- 音频重命名为 construction_complete.ogg (MC资源路径只允许小写/数字/下划线/横线/点, 原名含空格与大写)
- 音频置于 ra2 命名空间, 与create解耦, 为后续RA2语音系列包留扩展位
- JSON不支持注释, 所有决策记录于本文件

## 结构
三阵营独立包, 目录后缀 (Eva)(Zofia)(Yuri), 仓库根放GOAL-PLAN.md/README等工程文件不进包; 每包独立打zip(只压缩该包内层内容, pack.mcmeta必须位于压缩包根); sounds.json 三包相同(ra2:construction_complete + pitch 1.4286), 仅音频与 pack.mcmeta 描述后缀不同:
./Create-Schematicannon-RA2-Voice-Construction-Complete-(Eva)/pack.mcmeta
./Create-Schematicannon-RA2-Voice-Construction-Complete-(Eva)/assets/create/sounds.json
./Create-Schematicannon-RA2-Voice-Construction-Complete-(Eva)/assets/ra2/sounds/construction_complete.ogg
./Create-Schematicannon-RA2-Voice-Construction-Complete-(Zofia)/...同构
./Create-Schematicannon-RA2-Voice-Construction-Complete-(Yuri)/...同构
源音频: Eva=F:\Download\RA2 ceva048.ogg(已实测), Zofia=F:\Download\RA2 csof048.ogg, Yuri=F:\Download\RA2 cyur048.ogg

源音频: F:\Download\Video\RA2 ceva048.ogg (10.2KB)

## 已知限制
- Forge 下资源包 sounds.json 按条目与模组文件合并, 最小覆盖成立; Fabric 无此机制, 资源包的 sounds.json 会整体替换 Create 的全表(其余音效全部丢失), 本包按 Forge 设计, 不做 Fabric 适配, 仅在此提示
- Create 以固定 pitch 0.7 播放该事件 (AllSoundEvents.java: playExisting(NOTE_BLOCK_BELL, 1, .7f)), 语音被降调约6半音; 修复: 资源包 sound 条目加 pitch 1.4286 (乘法补偿, 0.7×1.4286≈1.0000, 偏差约0.03音分, 不可感知), 单一调用点无副作用

## 进度
- [x] 搭建资源包结构
- [x] 验证 ogg 为 Vorbis 编码 (1.20.1 不支持 Opus) — 已验: OggS容器/vorbis编码/单声道22050Hz, 无需转码
- [x] 游戏内实测 — 复测通过: 触发成功 + pitch 1.4286 补偿后音高恢复, 项目验收完成
- [x] git init + GitHub 发布, MPL-2.0 — https://github.com/LMaxRouterCN/Create-Schematicannon-RA2-Voice-Construction-Complete (main + tag v1.0.0 + Release 含 zip)
- [x] 三阵营版本: 已构建+推送 (d949195); v1.0.0 单release挂三zip, 资产名被GitHub服务端改写为-.Eva/-.Zofia/-.Yuri(括号被吃, 用户拍板接受), 发布完成; 待游戏内三包实测
## 后续需求: 替换加农炮 Start/Pause/Stop 按钮音效(已取消 — 用户决定不做; launch_block 为发射爆炸声亦不换; 以下留档备用)
- Create sounds.json 无按钮专属条目(仅 schematicannon_finish / schematicannon_launch_block 两个)
- launch_block 可换: 方法同 finish(覆盖 create:schematicannon_launch_block 条目, 注意其调用 playExisting 可能带非1参数需补偿), 未做
- 按钮音效定位中, 三分支:
  1. Create 注册型通用事件(confirm/deny类, 有条目) → 资源包可换
  2. 原版事件直连(ui.button.click类) → 仅可全局覆盖(影响全GUI按钮,不可取)或写 mixin 模组
  3. IconButton 覆盖 playDownSound 走自有事件 → 可换
- 定位法: 开字幕点按钮看 create.subtitle.xxx / 翻 SchematicannonScreen.java 与 IconButton.java 的 sound 调用
- 素材注意: 按钮音需短音(RAU acknowledge 类 0.3s 级), Construction complete 过长