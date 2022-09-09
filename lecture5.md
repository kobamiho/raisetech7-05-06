# Raisetech 第5回課題
## Rails Sample AppをEC2にデプロイ
* Webサーバー（Nginx）＆ APサーバー（Unicorn）の構成
* ELB追加。ブラウザからのHTTPリクエストをELB経由でターゲット（EC2）へ転送するようルーティング

![Rails App](../images/images_for_github/Lesson5-RailsApp.png)

* NginxとUnicronの自動起動設定（systemd）
* Active Storageを使ってAppにアップロードされる画像の保存先をS3へ。

![Nginx＆Unicorn自動起動＆AWS CLI](../images/images_for_github/Lesson5-Terminal.png)

* AWS構成図

![AWS構成図](../images/images_for_github/Lesson5-aws-diagram.png)


## <感想>
systemdでUnicornの自動起動設定をしたらコマンド操作がシンプルで楽になった。
が、systemdでデーモン化するならunicornじゃなくてデフォルトのpumaでよかったんじゃない?!
(unicornはコマンドが長くなるから好きじゃないww)
