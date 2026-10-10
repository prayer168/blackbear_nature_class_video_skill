# personal-footage-flow-video

> 直接分析使用者資料夾內拍攝的影片與照片，依提示詞剪輯成片；需要角色動畫或補充畫面時，可選用 Google Flow 生成再合成。

**版本：** 1.0.0
**日期：** 2026-10-10

## 用途

這個技能服務已經拍好素材、希望快速完成紀錄影片的工作流。它和教學頻道企劃技能不同：不預設腳本、旁白、字幕、SEO、品牌片頭或發布包，重點是素材分析、時間線、照片／影片混剪、可選的 Flow 生成內容、音樂權利和本機成片檢視。

## 工作流程

1. 讀取使用者指定資料夾並盤點照片、影片和音訊。
2. 以代表縮圖理解場景和可用片段，建立素材表與剪輯順序。
3. 依提示詞規劃節奏、畫幅、環境聲、配樂、轉場及可選疊圖。
4. 如有需要，使用者在 Google Flow 生成短角色／補充片段；先估點數和試片，再合成。
5. 核對音樂逐曲授權，混音並輸出影片。
6. 檢視轉場、音訊、角色遮罩、黑幀、片長與播放完整性，交付成片和來源紀錄。

## 使用方式

將整個資料夾安裝到 Codex 可發現的 skills 目錄，或將 `SKILL.md` 提供給支援技能的代理工具。使用者可直接說：

```text
請分析 D:\影片\海邊散步 裡面的影片與照片，剪成一支三分鐘黃昏紀錄片，不要字幕和旁白，保留現場聲，最後一分鐘加入 CC0 輕音樂。
```

## 授權和點數

- CC0／公有領域與免署名平台授權是不同情況；依曲目頁面和授權原文記錄。
- Google Flow 模型、費用和點數可能變動；以操作當下介面為準，不把舊估算當保證。
- 不包含破解受限內容、移除浮水印或繞過平台限制的流程。

## 專案文件

- `SKILL.md`：技能指令與製作流程
- `HISTORY.md`：版本歷史
- `VERSION`：目前 SemVer 版本

## GitHub 發布

## Git 與版本管理

此技能以獨立 Git repository 維護。版本遵循 SemVer，並同步更新 `VERSION`、`SKILL.md` 和本檔；每次發布在 `HISTORY.md` 記錄變更。

目前遠端：[`prayer168/blackbear_nature_class_video_skill`](https://github.com/prayer168/blackbear_nature_class_video_skill)
主要分支：`main`

一般更新流程：

```bash
git status --short --branch
git diff --check
git add SKILL.md README.md HISTORY.md VERSION
git commit -m "Describe the skill update"
git push origin main
```

初次 clone：

```bash
git clone https://github.com/prayer168/blackbear_nature_class_video_skill.git
```

此 repo 僅包含技能文件；拍攝素材、Flow 生成影片、音樂及成片應留在各自的影片專案資料夾，不提交到技能 repo。
