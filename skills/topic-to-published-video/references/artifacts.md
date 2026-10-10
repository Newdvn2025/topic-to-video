# 项目文件与交付物

推荐目录结构：

```text
项目名/
├── production-state.md
├── 00-brief.md
├── 01-script.md
├── 02-transcript.srt
├── 02-transcript.json
├── 03-design.md
├── 04-storyboard.md
├── 05-asset-manifest.json
├── 06-review.md
├── 07-cover-copy.md
├── 08-social-copy.md
├── input/
├── assets/
│   ├── a-roll/
│   ├── b-roll/
│   ├── images/
│   ├── music/
│   └── sfx/
└── out/
    ├── review/
    ├── final/
    └── covers/
```

## 唯一真源

- `01-script.md`：口播文字唯一真源。
- `02-transcript.json`：正式时间与卡点唯一真源。
- `03-design.md`：色彩、字体、卡片、字幕、图解与动效唯一真源。
- `04-storyboard.md`：画面和素材对应关系唯一真源。
- `05-asset-manifest.json`：生成任务与本地素材映射唯一真源。

任何用户修改都要更新相应文件。若修改会影响下游，例如口播变更导致字幕和分镜失效，在 `production-state.md` 中把下游阶段重新标记为待更新。

## production-state.md 模板

```markdown
# Production State

- topic:
- platform:
- aspect_ratio:
- target_duration:
- current_stage:
- script_locked: false
- transcript_timed: false
- design_locked: false
- storyboard_locked: false
- review_approved: false
- cover_copy_locked: false

## Locked decisions

## Inputs

## Latest outputs

## Pending confirmation

## Next action
```

## 分镜条目模板

```markdown
### S03｜00:12.400–00:18.200｜概念演示

- 口播原文：
- 叙事目的：
- 主画面：
- 解释画面：
- 构图/动作：
- 屏幕文字：
- 持续动态：
- 转场：
- 素材 ID：
- 风险：
```

## 素材清单最小字段

```json
{
  "id": "S03-B01",
  "purpose": "演示当前概念的可见变化",
  "voiceover_range": "00:12.400-00:18.200",
  "type": "video",
  "generator": "configured-provider",
  "prompt": "...",
  "duration": 5,
  "aspect_ratio": "16:9",
  "status": "planned",
  "local_path": null
}
```

## 最终交付报告

最终回复至少列出：

- 成片路径、时长、尺寸、帧率、编码和音轨状态。
- 字幕、项目源文件、封面和发布文案路径。
- 使用了哪些用户素材和生成素材。
- 已完成的关键质量检查。
- 仍存在的限制或可选优化项。
