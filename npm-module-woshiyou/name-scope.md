---
description: npm package の名前をつける際に name-scope の仕組みを使用することで、他パッケージと名前がバッティングすることを防げます。
---

# name-scope

{% embed data="{\"url\":\"https://docs.npmjs.com/misc/scope\",\"type\":\"link\",\"title\":\"scope \| npm Documentation\",\"description\":\"The place where all things npm are documented\",\"icon\":{\"type\":\"icon\",\"url\":\"https://docs.npmjs.com/images/favicon.ico\",\"aspectRatio\":0}}" %}

npm package を公開する際には package.json の name が「パッケージの名前」として使用され、この名前で registry に登録されますが、この名前は他のパッケージ名と被ってはいけません。なので、他の人に先に取られてしまっていると問題です。

そこで name-scope という仕組みを活用しましょう。

「@自分の npm account 名/パッケージ名」という形式に name を変更しましょう。この @youraccount   は、そのアカウントのユーザーにしか使用できませんので、他の人に使われる心配がありません。また、アカウント名以外にも organization 名を使うこともできます。

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
  "name": "@youraccount/package-name",
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

name-scope を使用したパッケージは

```bash
npm publish --access public
```

