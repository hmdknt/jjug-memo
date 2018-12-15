# マネーフォワードのアカウントアグリゲーションの現状と課題点について
## メモ　
### サービス
- アカウントアグリゲーション 
  - アカウントを一箇所に集める
  - 毎分5000万口座からアグリゲーション
    - 累計50億レコード

- ライブラリ
  - HtmlUnit
    - Javaで作られたGUI-Lessなブラウザ
    - 画面のレンダリング機能はない
    - UnitTestのフレームワークとして利用されることが多い
  
- 独自のブラウザ
  - 最新のブラウザと同じ動作ができるか
  - 常に最新のブラウザの状態にさせないといけない

# SeleniumWebDriverとヘッドレスChromeを用いたスクレイピング
## メモ
### ヘッドレスChromeの検討を始めた経緯
- OKHTTP などを利用した
- API連携でのアグリゲーションも増えてる
- スクレイピングの課題
  - HtmlUnitで対応しているのはEC3から？
  - リニューアル時にスクレイピングできないことが増えた

### ヘッドレスChromeの使い方
- ヘッドレスChrome
  - 

- 制御方法
  - node.js
    - pupeteer
  - java 
    - CDP(Chrome DevTools Protocol)
      - WebSocket通信
      - Jsonコマンド形式
      - CDPだけだとクリック操作が面倒
    - Selenium
      - 
      - 
  - Chromedriver
    - WebDraiver 標準API以外にも色々なAPIが定義されている
      - W3C standard endpoint
    - seleniumの使い方とほぼ同等

  - CDP
    - 
  - WebDraiver
    - ドキュメントが豊富
    - ライブラリが多い
- ファイルのダウンロード
- CDP

- WebDriver
  - 相互通信はできない

###
- chromeを閉じる処理を入れないとプロセスが立ち上がったまま
- ぺージ遷移が入るとHtmlUnitよりも早い？
- リソースを消費する
