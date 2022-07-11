https://vueschool.io/courses/vuejs-3-fundamentals

1. Getting Started with Vue.js 3
2. Using Vue DevTools with Vue.js 3

    - /etc/httpd/conf.d 配下の Alias は定義順で評価される
    - Laravel で '/' を定義するため、それ以降に Alias を定義しても無効（Apache のエラーログ参照）
    - 対策として、設定ファイルに数字のプリフィックスを付けた
    - Vue では Vue.createApp() でインスタンスを作成し、.mount() で body 内の id 要素と関連付ける
    - $vm0 ‥ Vue のグローバル識別子？ $vm0.data.header 等にアクセス可能
    - {{ }} (Double Mustache) で変数の展開を行う

3. Vue.js 3 template Syntax and Expressions

    - DevTools で実行しているのは development ビルド
    - 本番で動かす場合は production build (*.prod.js) のデプロイが必要
    - {{ }} (double mustache) 内に書ける評価式は一つだけ
    - {{ }} 内では変数の宣言はできない
    - if() による分岐はできないが、三項演算子 (a ? b : c) は利用可能
    - or 演算子も使える ( a || 'デフォルト値' )

4. List Rendering in Vue 3

    - 配列の定義と v-for によるイテレート。以下は同じ意味。どちらで書いてもよい：
        ```
        <li v-for="item in items" :key="item.id">{{item.label}}</li>
        <li v-for="{id, label} in items" :key="id">{{label}}</li>
        ```
    - vi-for でインデックスアクセス：
        ```
        <li v-for="(item, index) in items> :key="index">{{index}} {{item.label}}</li>
        ```
        - :key="index" は Vue 3 の内部的なデフォルトなので、書かなくても同じ。
        - セキュリティ上の理由で、key="index"は避けるべき
    - 配列として定義

        ```
          items: [
            {id: 1, label: "10 party hats"},
            {id: 2, label: "2 board games"},
            {id: 3, label: "20 cups"}
          ]
        ```

    - オブジェクトとして定義

        ```
          items: {
            'item-1': {id: 1, label: "10 party hats"},
            'item-2': {id: 2, label: "2 board games"},
            'item-3': {id: 3, label: "20 cups"}
          }
        ```

        さらにイテレートで index の代わりに key と書く
    - items への要素の追加：
        - shoppingLIstApp.items.push({id: 4, label: '1 awesome Vue course!'})
    - items からの要素の削除：
        - shoppingLIstApp.items.pop()