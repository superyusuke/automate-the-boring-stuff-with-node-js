# node でコマンドラインツールを作ろう

package.json に　"bin" :  { "command-name" : "to-path" } を追加することでシェルコマンドとして実行したときに、どのファイルを実行するかを指定します。ここでは "cli" という名前で実行すると、index.js が実行されるように指定しました。

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
    "bin": {
        "cli": "index.js"
    },
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

冒頭に \#!/usr/bin/env node をつけることで node で実行されるよう shell に伝えます。

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
#! /usr/bin/env node
console.log("cli ok!!");
```
{% endcode-tabs-item %}
{% endcode-tabs %}

#### 公開する

```bash
npm version minor # マイナーチェンジを行なったので
npm publish # 変更を公開
```

### npm package を使う

```bash
npm update @superyusuke/node-learn # 更新を取り込む
```

#### Local にインストールしたパッケージ使う方法2つ

#### npx を使う

```bash
npx cli
```

#### npm script に記述して使う

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
    "scripts": {
        "cli": "cli"
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

```bash
npm run cli
```

### npm link で symlink を作る

{% embed data="{\"url\":\"https://docs.npmjs.com/cli/link\",\"type\":\"link\",\"title\":\"link \| npm Documentation\",\"description\":\"The place where all things npm are documented\",\"icon\":{\"type\":\"icon\",\"url\":\"https://docs.npmjs.com/images/favicon.ico\",\"aspectRatio\":0}}" %}

package に変更があるたびに公開してupdate して…という手順を踏むのは面倒です。そこで npm link を活用します。

開発中のディレクトリで `npm link` 実行することで、npm が global にインストールされている場所から開発フォルダへの symlink を追加します。これによって、global にインストールされたコマンドのように実行することができます。

