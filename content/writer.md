---
title: "在线笔记本"
date: 2026-09-15
draft: false
---

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/easymde/dist/easymde.min.css">
<script src="https://cdn.jsdelivr.net/npm/easymde/dist/easymde.min.js"></script>

<textarea id="my-text-box"></textarea>
<br>
<button onclick="downloadMarkdown()" style="padding: 10px 20px; background: #007dfa; color: #fff; border: none; border-radius: 5px; cursor: pointer;">📥 下载为 Markdown 文件</button>

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
