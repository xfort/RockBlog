---
description: '记录奇形怪状的各类bug,以及一些坑'
---

# BUG！！！

1. `java.lang.IllegalStateException: Only fullscreen opaque activities can request orientation` 复现：android 8.0.0系统，设置 activity 的 windowIsTranslucent=true，切换屏幕方向（setRequestedOrientation\(ActivityInfo.SCREEN\_ORIENTATION\_PORTRAIT\)）时出现。 解决：设置windowIsTranslucent=false。这是8.0.0系统bug,已修复但很多厂家未跟进（例如华为部分手机） 
2. `读取meta 整数时乱码或异常` AndroidManifest.xml中 meta-data 中存放的数字，就不要用 getString\(\)去读取; 数据类型只支持String 、int、float、boolean; 若数值过大，getInt\(\)会返回0，不支持getLong\(\);

