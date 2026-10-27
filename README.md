# 星火英语 (Spark English)

一个单文件离线英语学习的 Android APP：**单词分组记忆** + **句子语法解读** + **语法参考**。

- 词汇记忆：22 个分类、5117 个四级单词，支持分类筛选、搜索、仅看未掌握，记忆进度本地保存。
- 语法解读：输入英文句子，自动标注词性、判定句型 / 时态 / 语态 / 主宾语 / 谓语动词。
- 语法参考：19 个语法章节，可搜索、可定位。

## 技术实现
- 核心是一个单文件 `index.html`（HTML + CSS + JS，零外部依赖，可离线运行）。
- Android 端用 `WebView` 直接加载 `app/src/main/assets/index.html`，无需联网。

## 本地构建 APK
```bash
# 需要 JDK 17 与 Android SDK（platform-34 / build-tools 34.0.0）
./gradlew assembleDebug
# 产物：app/build/outputs/apk/debug/app-debug.apk
```

## 通过 GitHub Actions 构建
推送 `main` 分支即自动触发 `.github/workflows/build.yml`，构建完成后在 **Releases** 中下载 `app-debug.apk`。
