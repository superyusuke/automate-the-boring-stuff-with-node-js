---
description: ターミナルへの表示を装飾するライブラリを紹介します。
---

# 装飾する

```javascript
// アスキーアートを出力できるライブラリ
const figlet = require("figlet");
// 色をつけられるプラグイン
const chalk = require("chalk");

// figlet がアスキーアートを出力する
console.log(
  chalk.red(
    figlet.textSync("My First CLI", {
      horizontalLayout: "full"
    })
  )
);

// chalk は色をつける
console.log(chalk.blue("Hi this is Blue Message"));
```

