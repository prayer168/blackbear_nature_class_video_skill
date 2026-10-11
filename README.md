# blackbear_nature_class_video_skill

> 直接分析使用者資料夾內拍攝的影片與照片，依提示詞剪輯成片；需要角色動畫或補充畫面時，可選用 Google Flow 生成再合成。

**版本：** 1.6.0
**日期：** 2026-10-11

## 用途

這個技能服務已經拍好素材、希望快速完成紀錄影片的工作流。它和教學頻道企劃技能不同：不預設腳本、旁白、字幕、SEO、品牌片頭或發布包；每支主片完成後延伸製作三支 Shorts；正片和每支 Shorts 都有各自的 YouTube 上架文案與 Facebook 貼文 TXT。重點是素材分析、時間線、照片／影片混剪、可選的 Flow 生成內容、音樂權利和本機成片檢視。

## 工作流程

1. 讀取使用者指定資料夾並盤點照片、影片和音訊。
2. 以代表縮圖理解場景和可用片段，建立素材表。
3. **先選定配樂或確認無配樂**；核對曲目授權、下載並確認音檔可讀取。
4. 配樂就緒後，依提示詞規劃剪輯時間線與畫面節奏。
5. 如有需要，再使用 Google Flow 生成角色／補充片段；先估點數、試片和檢視結果。
6. 混音輸出後，檢查畫面、環境聲、配樂、角色遮罩、片長與播放完整性。
7. 以主影片名稱建立根目錄，固定建立 `00 正片`、`01 Shorts`、`02 Shorts`、`03 Shorts`，各自有製作前／製作中／製作後與未來 YouTube 上傳檔案。
8. 主片輸出後，依不同亮點剪製三支獨立直式 Shorts，分別輸出正式 MP4、逐字稿、字幕、縮圖及上架文案；按當下 YouTube Shorts 官方規格設定，檢查裁切和字幕安全區。
9. 每支完成的正片或 Shorts 各自產生一份 Facebook 貼文純文字檔，保存於 `製作後/臉書宣傳/臉書貼文.txt`；文案不得虛構連結或片中未發生的事。
10. 正片及每支 Shorts 都建立各自的 YouTube 上架文案，供將來上傳；不自動登入、上傳或公開。

完整結構與命名見 [references/project-layout.md](references/project-layout.md)。上架標題、說明欄、Tags、置頂留言整合為一份 `上架文案.txt`；無口白影片不虛構台詞，每支主片預設剪製三支 Shorts；若使用者略過或素材不足，清楚記錄原因。

## 使用方式

將整個資料夾安裝到 Codex 可發現的 skills 目錄，或將 `SKILL.md` 提供給支援技能的代理工具。使用者可直接說：

```text
請分析 D:\影片\海邊散步 裡面的影片與照片，剪成一支三分鐘黃昏紀錄片，不要字幕和旁白，保留現場聲，最後一分鐘加入 CC0 輕音樂。
```

## 授權和點數

- CC0／公有領域與免署名平台授權是不同情況；依曲目頁面和授權原文記錄。
- Google Flow 模型、費用和點數可能變動；以操作當下介面為準，不把舊估算當保證。
- 不包含破解受限內容、移除浮水印或繞過平台限制的流程。
- YouTube 上架包是可選交付；章節須按最終影片核時，並記錄音樂授權與 Content ID 狀態。

## 專案文件

- `SKILL.md`：技能指令與製作流程
- `HISTORY.md`：版本歷史
- `VERSION`：目前 SemVer 版本

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
