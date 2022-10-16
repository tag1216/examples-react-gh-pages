# examples-react-gh-pages

Reactアプリを Github Pages にデプロイ

## 参考
- [Reactアプリをgithub Pages, Actionsでデプロイ | そーたの技術ブログ](https://blog.so-ta.net/portfolio/react-github-pages-actions/)
- [GitHub PagesにReactアプリをデプロイする方法 - Qiita](https://qiita.com/yuitnnn/items/11375ea29ec023d19fdf)

## 作成手順

- githubにリポジトリを作成
- 最新nodeのインストール  
    ```
    $ nvm install node
    $ nvm use node
    $ node -v
    v18.11.0
    ```
- リポジトリのclone  
    ```
    $ git clone git@github.com:tag1216/examples-react-gh-pages.git
    ```
- Reactアプリの作成  
    ```
    $ npx create-react-app examples-react-gh-pages --template typescript
    $ cd examples-react-gh-pages.git
    ```
- gh-pageのインストール
    ```
    $ npm install -D gh-pages
    ```
- gh-pages設定  
    package.json
    ```diff
    +   "homepage": "https://tag1216.github.io/examples-react-gh-pages",
    +    "predeploy": "npm run build",
       "scripts": {
    +    "deploy": "gh-pages -d build"
       }
    ```
- デプロイ
    ```
    $ npm run deploy
    ```
- github pages 設定

    - https://github.com/tag1216/examples-react-gh-pages/settings/pages
        - Source > Deploy from branch
        - Branch > gh-pages
