---
title: Pipe stdin NodeJS Commander
date: 2021-09-15 14:13:00 -500
categories: [javascript]
tags: [commandline,pipe]
---
```javascript
fs.readFileSync(process.stdin.fd, "utf-8")
```
