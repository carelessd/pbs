---
title: "第一期"
date: 2026-09-10T08:00:00Z
draft: false
audio_url: "https://podcast-bzm.pages.dev/audio.m4a"
audio_length: "8912345" # 音频文件大小（字节），可在文件属性里查看
audio_type: "audio/mp4" # 如果是 m4a 填 audio/mp4，mp3 填 audio/mpeg
---

<item>
  <title>{{ .Title }}</title>
  <link>{{ .Permalink }}</link>
  <pubDate>{{ .Date.Format "Mon, 02 Jan 2006 15:04:05 MST" }}</pubDate>
  <guid>{{ .Permalink }}</guid>
  <description>{{ .Summary | html }}</description>
  {{ with .Params.audio_url }}
  <enclosure url="{{ . }}" length="{{ $.Params.audio_length }}" type="{{ $.Params.audio_type }}"/>
  {{ end }}
</item>
