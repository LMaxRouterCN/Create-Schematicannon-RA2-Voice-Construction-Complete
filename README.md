# Create Schematicannon: RA2 Voice — Construction Complete

A Minecraft resource pack that replaces the Create mod's Schematicannon "printing finished" chime with the classic *Red Alert 2* EVA voice line: **"Construction complete."**

[English](#english) | [中文](#中文)

## English

A Minecraft resource pack that replaces the Create mod's Schematicannon "printing finished" chime with the classic *Red Alert 2* EVA voice line: **"Construction complete."**

### Features

- Replaces `create:schematicannon_finish` (the note block bell) with the RA2 EVA voice line
- Pitch-corrected: Create plays this event at a hardcoded 0.7 pitch (about -6 semitones). The pack compensates with a 1.4286 multiplier, so the voice plays at its natural pitch (residual deviation ~0.02 cent — imperceptible)

### Requirements

- Minecraft 1.20.1
- [Create](https://modrinth.com/mod/create) 0.5.1 for 1.20.1

### Install

**Folder:** copy the `Create-Schematicannon-RA2-Voice-Construction-Complete` folder into your instance's `resourcepacks/` directory.

**Zip:** compress the *contents* of that folder (so `pack.mcmeta` sits at the archive root), drop the zip into `resourcepacks/`, enable it in-game.

Then let a Schematicannon finish printing a schematic — and listen.

### How it works

- `assets/create/sounds.json` overrides the `schematicannon_finish` entry with `replace: true`, pointing to a custom sound in the `ra2` namespace
- The audio file lives at `assets/ra2/sounds/construction_complete.ogg` (Vorbis, mono, 22050 Hz)
- `pitch: 1.4286` on the sound entry cancels out Create's hardcoded 0.7 playback pitch

### Credits & licensing

- Files authored for this pack are licensed under the [MPL-2.0](LICENSE)
- The voice line and audio are assets of *Command & Conquer: Red Alert 2* (© EA / Westwood Studios). This is a non-commercial fan work for personal use, not affiliated with or endorsed by EA.

---

## 中文

一个 Minecraft 资源包：把机械动力（Create）蓝图加农炮"打印完成"的音符盒钟声，替换为红色警戒2里那声经典的 EVA 语音——**"建造完毕。"**

### 功能

- 将 `create:schematicannon_finish`（原音符盒钟声）替换为红警2 EVA 语音
- 音调已修正：Create 以硬编码的 0.7 音调播放该事件（约降低 6 个半音），本资源包用 1.4286 的乘数补偿，使语音以原始音调播放（残余偏差约 0.02 音分，无法察觉）

### 环境要求

- Minecraft 1.20.1
- [Create（机械动力）](https://modrinth.com/mod/create) 1.20.1 版 0.5.1

### 安装

**文件夹方式：** 把 `Create-Schematicannon-RA2-Voice-Construction-Complete` 文件夹整个复制到实例的 `resourcepacks/` 目录。

**Zip 方式：** 压缩该文件夹的*内容*（保证 `pack.mcmeta` 位于压缩包根），把 zip 放进 `resourcepacks/`，在游戏内启用。

然后让蓝图加农炮打印完一张蓝图——听。

### 实现原理

- `assets/create/sounds.json` 用 `replace: true` 覆盖 `schematicannon_finish` 条目，指向 `ra2` 命名空间下的自定义音效
- 音频文件位于 `assets/ra2/sounds/construction_complete.ogg`（Vorbis，单声道，22050 Hz）
- 音效条目上的 `pitch: 1.4286` 抵消 Create 硬编码的 0.7 播放音调

### 致谢与许可

- 本资源包编写的文件采用 [MPL-2.0](LICENSE) 许可
- 语音及音频素材来自《命令与征服：红色警戒2》（© EA / Westwood Studios）。本作为非商业性质的粉丝同人作品，仅供个人使用，与 EA 无关联、亦未获其认可。