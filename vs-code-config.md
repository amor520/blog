---
title: vs code config
tags:
  - config
  - vs
categories:
  - vs
  - config
---

{% cq %}
我们不得不饮食睡眠游惰恋爱，也就是说，我们不得不接触生活中最甜蜜的事情：不过我们必须不屈服于这些事物……
— 约里奥·居里
{% endcq %}
<!-- more -->
```
// 将设置放入此文件中以覆盖默认设置
{
    // 控制字体系列。
    "editor.fontFamily": "Meslo LG M for Powerline",
    // 控制字体粗细。
    "editor.fontWeight": "normal",
    // 控制字体大小。
    "editor.fontSize": 16,
    // 自定义要在 OS X 上运行的终端应用程序。
    "terminal.external.osxExec": "iTerm.app",
    // 控制是否自动保存更新后的文件。接受的值:“off”、“afterDelay”、“onFocusChange”(编辑器失去焦点)、“onWindowChange”(窗口失去焦点)。如果设置为“afterDelay”，则可在 "files.autoSaveDelay" 中配置延迟。
    "files.autoSave": "afterDelay",
    // 启用要发送给 Microsoft 的使用情况数据和错误。
    "telemetry.enableTelemetry": false,
    // 启用要发送给 Microsoft 的故障报表。
    // 此选项需重启才可生效。
    "telemetry.enableCrashReporter": false,
    // Automatically update extensions
    "extensions.autoUpdate": true,
// Go configuration
    // Autocomplete members from unimported packages.
    "go.autocompleteUnimportedPackages": true
}
```