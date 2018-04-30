# Untitled

### commander のインストール

```bash
npm i commander # -D ではだめ
```

かならず dependencies に追加します。 -D で devDependencies に追加してはいけません。そうした場合、このパッケージに必要なパッケージが、この npm を使っているユーザー側でインストールされません。

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



