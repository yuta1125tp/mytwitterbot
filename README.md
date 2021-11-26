# HEROKUを利用したTwitter Bot

# ローカルで動くか確認するとき
```cmd
heroku run python tweet.py
```

# botの内容をherokuへ反映するとき
```cmd
git add 変更を加えたファイル
git commit -m "変更内容を簡潔にコメント"
git push heroku master
```

# 作業メモ
Windows 11 64bit 
[64bit用インストーラ](https://devcenter.heroku.com/ja/articles/heroku-cli)をダウンロード。
選択肢はデフォルトのまま、「CLIをインストール」「パスに追加する」「＊＊＊（後なにかあったが無害そうな選択肢）」の３つのチェックボックスが有効な状態

インストール後はコマンドプロンプトで`heroku login`を実行して認証を済ませる。

\*1を参考にファイルを用意した後`heroku create`を実行した。最新のインストーラからインストールしたがバージョンが古いらしい。`heroku update`で7.59.2へアップデートできた。

```cmd
heroku_demo>heroku create
 »   Warning: heroku update available from 7.53.0 to 7.59.2.
Creating app... done, ⬢ ********-*****-*****
https://********-*****-*****.herokuapp.com/ | https://git.heroku.com/********-*****-*****.git

heroku_demo>heroku update
heroku: Updating CLI from 7.53.0 to 7.59.2... done
heroku: Updating CLI... done

heroku_demo>git push heroku master
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 1.76 KiB | 450.00 KiB/s, done.
Total 8 (delta 0), reused 0 (delta 0), pack-reused 0
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----> Building on the Heroku-20 stack
remote: -----> Determining which buildpack to use for this app
remote: -----> Python app detected
remote: -----> Using Python version specified in runtime.txt
remote:  !     Python has released a security update! Please consider upgrading to python-3.9.9
remote:        Learn More: https://devcenter.heroku.com/articles/python-runtimes
remote: -----> Installing python-3.9.1
remote: -----> Installing pip 21.3.1, setuptools 57.5.0 and wheel 0.37.0
remote: -----> Installing SQLite3
remote: -----> Installing requirements with pip
remote:        Collecting bottle==0.12.9
remote:          Downloading bottle-0.12.9.tar.gz (69 kB)
remote:          Preparing metadata (setup.py): started
remote:          Preparing metadata (setup.py): finished with status 'done'
remote:        Collecting certifi==2017.4.17
remote:          Downloading certifi-2017.4.17-py2.py3-none-any.whl (375 kB)
remote:        Collecting chardet==3.0.3
remote:          Downloading chardet-3.0.3-py2.py3-none-any.whl (133 kB)
remote:        Collecting idna==2.5
remote:          Downloading idna-2.5-py2.py3-none-any.whl (55 kB)
remote:        Collecting oauthlib==2.0.2
remote:          Downloading oauthlib-2.0.2.tar.gz (125 kB)
remote:          Preparing metadata (setup.py): started
remote:          Preparing metadata (setup.py): finished with status 'done'
remote:        Collecting requests==2.17.3
remote:          Downloading requests-2.17.3-py2.py3-none-any.whl (87 kB)
remote:        Collecting requests-oauthlib==0.8.0
remote:          Downloading requests_oauthlib-0.8.0-py2.py3-none-any.whl (23 kB)
remote:        Collecting urllib3==1.21.1
remote:          Downloading urllib3-1.21.1-py2.py3-none-any.whl (131 kB)
remote:        Building wheels for collected packages: bottle, oauthlib
remote:          Building wheel for bottle (setup.py): started
remote:          Building wheel for bottle (setup.py): finished with status 'done'
remote:          Created wheel for bottle: filename=bottle-0.12.9-py3-none-any.whl size=87254 sha256=6731128a0157c36c4e0a8737b4562c1084f340e48d96c9a246ea6f116bcaac27
remote:          Stored in directory: /tmp/pip-ephem-wheel-cache-ckpr2p26/wheels/c5/e2/3a/b5cddd052c0c50c42724af0fb48db179a45eb0ef75ef3b1550
remote:          Building wheel for oauthlib (setup.py): started
remote:          Building wheel for oauthlib (setup.py): finished with status 'done'
remote:          Created wheel for oauthlib: filename=oauthlib-2.0.2-py3-none-any.whl size=120153 sha256=288fbaefa4da2564fd2f92f9fea239a0f917f0b4e8d2a9a977c784c689ca2a6b
remote:          Stored in directory: /tmp/pip-ephem-wheel-cache-ckpr2p26/wheels/b4/f8/75/856dc6c8bede617f69c86205c8a76c34ca955aa42974dcfa51
remote:        Successfully built bottle oauthlib
remote:        Installing collected packages: urllib3, idna, chardet, certifi, requests, oauthlib, requests-oauthlib, bottle
remote:        Successfully installed bottle-0.12.9 certifi-2017.4.17 chardet-3.0.3 idna-2.5 oauthlib-2.0.2 requests-2.17.3 requests-oauthlib-0.8.0 urllib3-1.21.1
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote:
remote: -----> Compressing...
remote:        Done: 53.2M
remote: -----> Launching...
remote:        Released v3
remote:        https://********-*****-*****.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy... done.
To https://git.heroku.com/********-*****-*****.git
 * [new branch]      master -> master

heroku_demo>heroku config:set CONSUMER_KEY=*** CONSUMER_SECRET=*** ACCESS_TOKEN_KEY=*** ACCESS_TOKEN_SECRET=***
Setting CONSUMER_KEY, CONSUMER_SECRET, ACCESS_TOKEN_KEY, ACCESS_TOKEN_SECRET and restarting ⬢ ********-*****-*****... done, v4

heroku_demo>heroku run python tweet.py
Running python tweet.py on ⬢ ********-*****-*****... up, run.7526 (Free)

heroku_demo>heroku addons:create scheduler:standard
Creating scheduler:standard on ⬢ ********-*****-*****... free
 To manage scheduled jobs run:
 heroku addons:open scheduler

Created scheduler-flexible-*****
Use heroku addons:docs scheduler to view documentation

heroku_demo>heroku addons:open scheduler
Opening https://addons-sso.heroku.com/apps/******/addons/********...
```



# 参考
[*1 Pythonで作ったTwitterのbotをHerokuで動かす](https://hwhw.hatenablog.com/entry/2017/06/04/234539)  
