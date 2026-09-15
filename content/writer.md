---
title: "在线笔记本"
date: 2026-09-15
draft: false
---

<!-- 注入柔和护眼的主题背景和样式 -->
<style>
    /* 整个网页背景变成柔和的米灰色/浅豆沙色，告别刺眼纯黑/纯白 */
    body, #content, main {
        background-color: #f4f6f0 !important;
        color: #2c3e50 !important;
    }
    /* 编辑器整体外框圆角与阴影优化 */
    .EasyMDEContainer {
        border-radius: 8px;
        overflow: hidden;
        box-shadow: 0 4px 12px rgba(0,0,0,0.05);
    }
    /* 让输入框内部也变得柔和护眼 */
    .CodeMirror {
        background-color: #fbfbf9 !important;
        color: #333333 !important;
        font-family: monospace;
        font-size: 15px;
    }
</style>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/easymde/dist/easymde.min.css">
<script src="https://cdn.jsdelivr.net/npm/easymde/dist/easymde.min.js"></script>

<div style="max-width: 800px; margin: 0 auto; padding: 20px;">
    <h2 style="color: #4a6b5d; text-align: center;">🌱 护眼在线笔记本</h2>
    <p style="text-align: center; color: #666; font-size: 14px;">随时随地写文章，写完点击下方按钮下载 .md 文件</p>
    
    <textarea id="my-text-box"></textarea>
    
    <div style="text-align: center; margin-top: 20px;">
        <button onclick="downloadMarkdown()" style="padding: 12px 24px; background: #5a8f76; color: #fff; border: none; border-radius: 6px; cursor: pointer; font-size: 16px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">📥 下载为 Markdown 文件</button>
    </div>
</div>

<script>
    var easyMDE = new EasyMDE({ element: document.getElementById('my-text-box') });

    function downloadMarkdown() {
        var content = easyMDE.value();
        var blob = new Blob([content], { type: "text/markdown;charset=utf-8" });
        var url = URL.createObjectURL(blob);
        var a = document.createElement("a");
        a.href = url;
        a.download = "new-post.md";
        a.click();
    }
</script>
