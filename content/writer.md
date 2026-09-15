---
title: "Markdown"
date: 2026-09-15
draft: false
---

## 🌱 护眼在线笔记本

随时随地写文章，写完点击下方按钮下载 `.md` 文件：

<textarea id="my-text-box" style="width: 100%; height: 350px; padding: 12px; font-size: 16px; border: 1px solid #b2bec3; border-radius: 6px; background-color: #fbfbf9; color: #2d3436; box-sizing: border-box; resize: vertical;"></textarea>

<div style="text-align: center; margin-top: 15px;">
    <button onclick="downloadMarkdown()" style="padding: 10px 20px; background: #5a8f76; color: #fff; border: none; border-radius: 6px; cursor: pointer; font-size: 16px;">📥 下载为 Markdown 文件</button>
</div>

<script>
    function downloadMarkdown() {
        var content = document.getElementById('my-text-box').value;
        var blob = new Blob([content], { type: "text/markdown;charset=utf-8" });
        var url = URL.createObjectURL(blob);
        var a = document.createElement("a");
        a.href = url;
        a.download = "new-post.md";
        a.click();
    }
</script>
