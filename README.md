# HEROKUを利用したTwitter Bot


# 環境設定
Windows 11 64bit 
[64bit用インストーラ](https://devcenter.heroku.com/ja/articles/heroku-cli)をダウンロード。
選択肢はデフォルトのまま、「CLIをインストール」「パスに追加する」「＊＊＊（後なにかあったが無害そうな選択肢）」の３つのチェックボックスが有効な状態

インストール後はコマンドプロンプトで`heroku login`を実行して認証を済ませる。

\*1を参考にファイルを用意した後`heroku create`を実行した。最新のインストーラからインストールしたがバージョンが古いらしい。`heroku update`で7.59.2へアップデートできた。

```bat
heroku_demo>heroku create
 »   Warning: heroku update available from 7.53.0 to 7.59.2.
Creating app... done, ⬢ ********-*****-*****
https://********-*****-*****.herokuapp.com/ | https://git.heroku.com/********-*****-*****.git

heroku_demo>heroku update
heroku: Updating CLI from 7.53.0 to 7.59.2... done
heroku: Updating CLI... done
```



# 参考
[*1 Pythonで作ったTwitterのbotをHerokuで動かす](https://hwhw.hatenablog.com/entry/2017/06/04/234539)  
