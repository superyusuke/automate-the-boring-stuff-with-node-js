# npm module を公開しよう

### npm registry のアカウントを作ろう

[https://docs.npmjs.com/getting-started/publishing-npm-packages](https://docs.npmjs.com/getting-started/publishing-npm-packages)

まずは npm registry のアカウントを作ります。terminal で以下のコマンドを実行します。

```bash
npm adduser
```

次の項目を聞かれるので、入力します。E-mail アドレスは公開される点に注意してください。

```text
Username: superyusuke
Password:
Email: (this IS public) super.yusuke0000@gmail.com
```

mail の verification が送られてくるので、メールに添付された URL をクリックして verification しましょう。

### package.json を作ろう

以下のコマンドを terminal で実行します。

```bash
npm init -y
```

これで全ての項目を仮に埋めた package.json ができます。

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
  "name": "your-package-name",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "dependencies": {},
  "devDependencies": {},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

name が特に重要で、これが公開されるパッケージ名になりますので、任意の名前に変更しましょう。

### node module を作ろう

次に node module を作ります。

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
module.exports = val => {
  console.log(val);
};
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### npm package を公開しよう

```bash
npm publish --access public
```

これで npm registry にあなたの npm package が公開されました。

### npm を インストールして使おう

先ほどのプロジェクトとは別の、新規プロジェクトを作って、先ほど公開した npm package をインストールして使用します。

```bash
npm install package-name -D
```

require で install した package を読み込んで使用します。

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
const yourModule = require("your-package-name");
yourModule("cant kkk");
```
{% endcode-tabs-item %}
{% endcode-tabs %}

以下のコマンドで実行しましょう。

```bash
node index.js
```



