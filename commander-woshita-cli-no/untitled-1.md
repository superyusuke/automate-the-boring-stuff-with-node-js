# 装飾する

```javascript
const figlet = require("figlet");
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

