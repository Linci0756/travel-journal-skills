# Travel Journal Skills

从旅行手记网站的维护流程拆出的四个独立 Codex Skills。每个目录包含自己的 `SKILL.md`，可以单独分发或放在同一个 GitHub 仓库中。

| Skill | 负责什么 | 调用示例 |
| --- | --- | --- |
| [journey-content-data](skills/journey-content-data/SKILL.md) | 手记标题、章节、照片信息、目录及路线来源 | `$journey-content-data 为现有网站增加一篇旅程，未知内容明确待补。` |
| [journey-theme-design](skills/journey-theme-design/SKILL.md) | 目的地配色、地图配色、背景融合和文字对比度 | `$journey-theme-design 只调整这篇旅程的主题颜色。` |
| [scroll-story-map](skills/scroll-story-map/SKILL.md) | 滚动联动、路线进度、到站聚焦、镜头与地图交互 | `$scroll-story-map 检查地图抖动并保留到站放缩。` |
| [local-static-preview](skills/local-static-preview/SKILL.md) | localhost 服务、静态路由、资源加载与预览恢复 | `$local-static-preview 恢复当前网站的 localhost 预览。` |

上传 GitHub 时保留 `skills/<skill-name>/SKILL.md` 的结构。单独分享某个 Skill 时，分享对应的子目录即可；每项已包含自己的项目适配信息，无需安装其他三项。

这些文件是工作指令，不是网站源码。仓库不包含旅行照片、真实轨迹、个人记录或凭据。发布网站或上传个人素材需要另行明确提出。
