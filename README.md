# Create Schematicannon: RA2 Voice — Construction Complete

[English](#english) | [中文](#中文)

## English

A Minecraft resource pack that replaces the Create mod's Schematicannon "printing finished" chime with the classic *Red Alert 2* adjutant voice line: **"Construction complete."**

### Features

- Replaces `create:schematicannon_finish` (the note block bell) with the RA2 adjutant voice line
- Pitch-corrected: Create plays this event at a hardcoded 0.7 pitch (about -6 semitones). The pack compensates with a 1.4286 multiplier, so the voice plays at its natural pitch (residual deviation ~0.02 cent — imperceptible)

### Requirements

- Minecraft 1.20.1
- [Create](https://modrinth.com/mod/create) 0.5.1 for 1.20.1

### Known limitation (Forge vs. Fabric)

Under Forge, a resource pack's `sounds.json` merges with the mod's file entry-by-entry, so this minimal override works. Fabric has no such mechanism — a resource pack's `sounds.json` fully replaces Create's entire sound table (all other Create sounds would be lost). This pack is designed for Forge; no Fabric adaptation is planned, and this note is the only accommodation.

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

一个简单的 Minecraft 资源包：把机械动力（Create）蓝图加农炮打印完成后的音符盒钟声，替换为红色警戒2的副官语音"Construction complete."

### 功能

- 将 `create:schematicannon_finish`（原音符盒钟声）替换为红警2副官语音
- 音调已修正：Create 以硬编码的 0.7 音调播放该事件（约降低 6 个半音），需要用 1.4286 的乘数补偿，使语音以原始音调播放（偏差约 0.02 音分，理论上听不出来）

### 已知限制（Forge 与 Fabric）

Forge 下资源包 sounds.json 按条目与模组文件合并，最小覆盖成立；Fabric 无此机制，资源包的 sounds.json 会整体替换 Create 的全表（其余音效全部丢失）。

>未经过实机测试,我不确定

### 安装

**文件夹方式：** 把 `Create-Schematicannon-RA2-Voice-Construction-Complete` 文件夹整个复制到实例的 `resourcepacks/` 目录。

**Zip 方式：** 压缩该文件夹（保证 `pack.mcmeta` 位于压缩包根目录），把 zip 放进 `resourcepacks/`，在游戏内启用。

### 实现原理

- `assets/create/sounds.json` 用 `replace: true` 覆盖 `schematicannon_finish` 条目，指向 `ra2` 命名空间下的自定义音效
- 音频文件位于 `assets/ra2/sounds/construction_complete.ogg`（Vorbis，单声道，22050 Hz）
- 音效条目上的 `pitch: 1.4286` 抵消 Create 硬编码的 0.7 播放音调

### 致谢与许可

- 本资源包编写的文件采用 [MPL-2.0](LICENSE) 许可
- 语音及音频素材来自《命令与征服：红色警戒2》（© EA / Westwood Studios）。本作为非商业性质的粉丝同人作品，仅供个人使用，与 EA 无关联、亦未获其认可。