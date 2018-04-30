# Untitled

### commander のインストール

```bash
npm i commander # -D ではだめ
```

かならず dependencies に追加します。 -D で devDependencies に追加してはいけません。そうした場合、このパッケージに必要なパッケージが、この npm を使っているユーザー側でインストールされません。

### ソースコード

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
// 追加したい場合
program.on("--help", () => {
  console.log("");
  console.log("  my fist CLI:");
});

// これで shell で実行する際に与えた引数をパースする
program.parse(process.argv);

// --path が指定されていた場合
if (program.path) {
  // option の arg はこれで取れる
  console.log(program.path);
}

if (program.target) {
  // target に arg をさらに渡していればの値が、
  // なければ true がかえってくる
  console.log(program.target);
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### コマンドラインで実行す

```bash
cli --path
# <path> と必須な arg がないためにエラーになる

cli --path test
# path があるのでコンソールに表示される

cli --target
# 追加の arg は必須ではないので OK
# true が表示される

cli --target test
# 追加の arg があるので、test と表示される
```

[https://arata.hatenadiary.com/entry/2016/01/17/010830](https://arata.hatenadiary.com/entry/2016/01/17/010830)



