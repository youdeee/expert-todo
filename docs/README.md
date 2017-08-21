# ExpertTodo
[Rails中級者向け勉強会Step-to-Rails-Expert.rb](https://step-to-rails-expert-rb.connpass.com/)のtodoアプリを作成しレビューしあう企画の元リポジトリです。
企画についての詳しい説明は、[説明ページ](http://biibiebisuke.hatenablog.com/entry/2017/08/08/173906)をご覧ください。

## アプリ名について
ExpertTodoという名前を使用すると環境にHerokuを使う場合など、アプリ名をurlに使う場合重複してしまい使用できない可能性があるので、任意のアプリ名を考えるか、`${account_name}-expert-todo`のアプリ名としてください。

## 開発の流れ
### 初めての方
- 本リポジトリをforkする
- 初回はmasterブランチにてrails newを行いcommit
- その後、reviewブランチを切ってそこで作業（reviewブランチから任意でブランチを切っても良い）

### 途中参加の方
以下のどちらかを選んで下さい。
- 「初めての方」の手順に従う
- 他の参加者のアプリをforkしてから実装する

## ルール
- GitHub上でコードを公開する
- 常に動作確認できる環境を作る
  - 他の人が簡単に動作確認できるようにするため
  - Heroku, AWS, ...etc
- 開発環境の構築手順を ルートディレクトリのREADMEに書く
  - 基本は bin/setup で構築できるようにする
- CI環境の構築
  - テストの量は自由
  - 使用するCIサービスは自由
- コミットメッセージの日本語、英語はどちらでも可
- UIに関しては、各々の裁量に任せる（ただし、使う上でソースを読まないと使えないものはダメ）
- データの整合性（既存データの保存を保証する）は任意。

#### 当日までに行うこと
- 実施当日までに、reviewブランチからmasterブランチへPRを送ってください。  
レビューは基本的にPRに対し行います。必要に応じてslack、口頭と分かれることはありますが、主にGitHubにて行います。
- 当日までに、Heroku等の環境にデプロイをお願いします。  
行っていない場合、レビューを円滑に行えない可能性があります。エラー等で出来なかった場合は、当日に質問すれば有益な答えをもらえると思うので、気兼ねなく聞いてください（デプロイをしなければレビューをしない、というわけではありません）。

上記を守っていない場合、レビュー希望者の数が多いときにレビューを行えない可能性があるので、可能な限り行って頂くようお願いします。  
上記を行わなかった、もしくは単に時間がなかった等の理由でレビューが間に合わなかった場合、その次参加して頂ける回で優先的にレビューを行う等の対応を行うつもりです。

## 仕様
順番に実装する必要はありません。他の人のをforkしても構いませんし、最初から自分の実装したい部分だけかいつまんでもらっても結構です。
### 最小機能（初期機能）（2017/09/25に実施）
- ユーザー認証ができる（email認証）
- タスクを登録、更新、削除できる
- タスクに期限日・説明を設定できる
    - 期限日・説明の設定は必須ではない（期限日のないタスク、説明のないタスク、両方ともないタスクが存在する）

### 第二回追加機能
- 必須: タスクの状態変更（単数タスク）  
タスクを終了済みにすることができる
- Level 1: 通常ユーザーの作成時に確認メールを送信する  
Sign up時に登録確認のメールを送ることができる
- Level 2 is: タスクへのファイルのアタッチ（複数）  
タスクに参考資料などのファイルを単数または複数アタッチすることができる
- Level 3 is: タスクの状態変更（複数一括）  
複数のタスクの状態（終了済みなど）をまとめて変更できる。終了済みから未終了への変更は任意です。