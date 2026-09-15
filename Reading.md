---
title: Reading EPUB
Date: 2026-09-16
draft: false
---

<!-- 引入 epub.js 所需的依赖库 -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.5/jszip.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/epubjs/dist/epub.min.js"></script>

<!-- 阅读器展示区域 -->
<div id="viewer" style="width: 100%; height: 700px; border: 1px solid #ccc; border-radius: 8px; background: #f9f9f9; position: relative;"></div>

<!-- 翻页控制按钮 -->
<div style="text-align: center; margin-top: 15px;">
    <button id="prev" style="padding: 8px 16px; cursor: pointer; margin-right: 10px;">◀ 上一页</button>
    <button id="next" style="padding: 8px 16px; cursor: pointer;">下一页 ▶</button>
</div>

<!-- 核心渲染脚本 -->
<script>
    // 你的 EPUB 直链
    var bookUrl = "https://pub-0509df5f3cfd4af996378bce549dbf15.r2.dev/1Q84-BOOK3-Cun-Shang-Chun-Shu.EPUB";

    // 初始化电子书
    var book = ePub(bookUrl);
    var rendition = book.renderTo("viewer", {
        width: "100%",
        height: "100%"
    });

    // 渲染第一页
    var displayed = rendition.display();

    // 绑定上一页按钮事件
    document.getElementById("prev").addEventListener("click", function(e){
        book.package.metadata.direction === "rtl" ? rendition.next() : rendition.prev();
        e.preventDefault();
    }, false);

    // 绑定下一页按钮事件
    document.getElementById("next").addEventListener("click", function(e){
        book.package.metadata.direction === "rtl" ? rendition.prev() : rendition.next();
        e.preventDefault();
    }, false);
</script>
