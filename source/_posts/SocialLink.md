---
title: Social Link设置
date: 2026-01-08 21:00:00
academics: "Rank 1"
academics_p: "w-[10%]"
charm: "Rank 2"
charm_p: "w-[20%]"
courage: "Rank 2"
courage_p: "w-[20%]"
---

> **Social Link:** 本文讲述了如何设置社群系统

---

### 01 / 存放友情链接

根目录的 `_config.yml` 中添加一个数据项，方便以后管理：

```c
# 友情链接数据
friends:
  - name: "幻影档案馆"
    url: "https://example.com"
    desc: "记录影时间的观测者"
    avatar: "https://api.dicebear.com/7.x/pixel-art/svg?seed=1"
  - name: "Velvet Room"
    url: "https://example.com"
    desc: "欢迎来到天鹅绒房间"
    avatar: "https://api.dicebear.com/7.x/pixel-art/svg?seed=2"
```

然后在`index.ejs`或者`layout.ejs`中添加相应的美化和引用，以后在`_config.yml`中即可方便的添加友情链接

---

