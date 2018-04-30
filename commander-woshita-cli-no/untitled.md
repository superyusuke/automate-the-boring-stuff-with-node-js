# Untitled

### commander のインストール

```bash
npm i commander # -D ではだめ
```

かならず dependencies に追加します。 -D で devDependencies に追加してはいけません。そうした場合、このパッケージに必要なパッケージが、この npm を使っているユーザー側でインストールされません。

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
#! /usr/bin/env node
// commander を用意する
const program = require("commander");

// commander に設定を追加していく
program
  .version("1.0.0", "-v, --version") // version の設定
  .option("-p, --path <path>", "description for path")
  .option("-t, --target [files]", "description for target");
  
  // -p or --path で与えられるオプションを設定する
  // <value> は必ず必要で [value] は任意
  

program
  .command("write [files...]") // command を使用する場合
  .description("write files.")
  .action(files => {
    files.forEach(file => console.log(file));
  });

// 基本的に help は自動で作成されるが
program.on("--help", () => {
  console.log("");
  console.log("  my fist CLI:");
});

program.parse(process.argv);

if (program.path) {
  console.log(program.path);
}

if (program.target) {
  console.log(program.target);
}

// console.log(
//   chalk.red(
//     figlet.textSync("My First CLI", {
//       horizontalLayout: "full"
//     })
//   )
// );
//
// console.log(chalk.blue("Hi this is Blue Message"));


```
{% endcode-tabs-item %}
{% endcode-tabs %}

[https://arata.hatenadiary.com/entry/2016/01/17/010830](https://arata.hatenadiary.com/entry/2016/01/17/010830)

```javascript
program
  .version("1.0.0")
  .option("-p --path <path>", "description for path")
  .option("-o --option [option]", "description for option");

program.parse(process.argv);

console.log(program.path, program.option);
// propgram.option が無いときにエラーになる。どうすればいいか。
// また [name] は結局使わない
```



