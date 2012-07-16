---
layout: post
title: "RubyMotionでよくある質問"
date: 2012-07-17 03:24
comments: true
categories: RubyMotion
---
RubyMotionでよく聞かれる質問をまとめてみました。

## Q1. いくらですか？
現在 ¥16,354 となっています。無料版もお試し版もありません。

学生や大企業は個別に連絡することで対応してくれるそうです。


## Q2. ライセンスは何年有効ですか？
サポート（アップデート含む）は年間契約です。継続料は通常料金の半額だそうです。

アップデートが不要であれば一度買えばずっと使えるわけですが、現実的には毎年¥8,000ちょいを払って継続することになります。


## Q3. Androidのアプリは作れる？
できません。今後その予定もありません。

公式サイトでもAndroidやりたい場合は [Ruboto](http://ruboto.org/) をチェックするようにとの旨書いてあります。


## Q4. オープンソースですか？
一部OSSです。[RubyMotion/RubyMotion](https://github.com/RubyMotion/RubyMotion)

これはRubyMotionのうちllvmを使ってRubyコードをバイナリにコンパイルするコマンドを実行するRakeタスクであって、RubyMotionのコンパイラ自体ではありません。

OSSでは無い部分も、多くはMacRubyと共通しているそうです。（MacRubyはOSSです。）


## Q5. 仕事で使えますか？
使えるといえば使えます。僕が仕事で作ったアプリは現在AppStoreでin reviewですし、次のアプリも作り始めています。

ただ、開発しながらRubyMotion自体のバグを見つけてしまってそれの再現ケースを作ったり、修正パッチを作ったりという作業もしています。  
でもそれは他のどのライブラリやフレームワークを使っていても一緒ですよね？


## Q6. メモリ管理まわりはどうなっていますか？
公式の情報によると、ARCと似たリファレンスカウンタ方式で自動的に管理してくれるそうです。

なので、僕ら開発者はメモリ管理をする必要はありません。逆に言うとできません。
やろうと思えば `obj.send(:retain)` とかも可能ですが、本来はそこはRubyMotionが面倒を見る部分なのであまりやらない方がいいと思います。

とは言いつつもメモリリークが疑われるようなときなどは `obj.retainCount` をログに出しながら開発したりしています。（で、おかしかったら再現ケースつくってサポートチケット投げる）


## Q7. Objective-C のコードに変換されるのですか？
いいえ。直接LLVMのバイトコードに変換されます。

実行速度的には有利ですが、RubyMotionがもし開発停止とかになったときにObjCのコードが手元に残らないというのは、Titaniumとの比較のときに考慮に入れるべきかもしれませんね。


## Q8. Apple の審査は通るのですか？
通ります。

公式で開発した [Mustachio](http://itunes.apple.com/us/app/mustachio/id525324802?mt=8) というアプリが AppStore で公開されていますし、今AppStoreの有料上位の [EverClip](http://clip.ignition.hk/) というアプリもRubyMotion製です。（BubbleWrapとかmotion-nanostoreとかのgemを使っているそうです。）


## Q9. Objective-C のライブラリは使えますか？
使えます。

[CocoaPods](http://cocoapods.org/)をmotion-cocoapodsというgemを利用すると使えるのでそれが一番手軽ですが、静的にコンパイルされたライブラリやXcodeのプロジェクトをそのまま使うことも可能です。


## Q10. 既存の gem は使えますか？
使えません。RubyMotion用に作られたgemを使ってください。あるいはObjective-Cのライブラリを探して使ってください。


他に追加したいFAQがありましたら @satococoa までお願いします。