---
title: "第一期"
date: 2026-09-10T08:00:00Z
draft: false
audio_url: "https://podcast-bzm.pages.dev/audio.m4a"
audio_length: "8912345" # 音频文件大小（字节），可在文件属性里查看
audio_type: "audio/mp4" # 如果是 m4a 填 audio/mp4，mp3 填 audio/mpeg
---

<div class="audio-player" style="margin: 20px 0;">
  <audio controls style="width: 100%;">
    <source src="{{ .Params.audio_url }}" type="{{ .Params.audio_type | default "audio/mp4" }}">
    您的浏览器不支持音频播放。
  </audio>
</div>
