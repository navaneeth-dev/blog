---
layout: post
title: Windows Persistence Techniques
image: /assets/malware.jpg
tags: windows malware persistence
---

Some persistence techniques from my ongoing research.

## COM Hijacking

Not detected by Autoruns. Use COMProxy PoC.

`{C93CF9D5-031B-4AAA-AB0B-EF802347B381}` - Startup hijack
`{A4173A49-F373-4475-9A0F-2D615204DC20}` - NetworkChangedState

Resources:
- [https://enigma0x3.net/2016/05/25/userland-persistence-with-scheduled-tasks-and-com-handler-hijacking/](https://enigma0x3.net/2016/05/25/userland-persistence-with-scheduled-tasks-and-com-handler-hijacking/)