[Notesホームに戻る](/notes)
* * *
# あなたの味方となるヘルプの見方のウェブページ
なんちって。  

面白くないですねハイすみませんでした。

## ウェブ版ヘルプとDiscord版ヘルプの違いについて
特にありません。  
表示とコマンドヘルプの順番がちょっと違ったりするだけです。

## 本編
![「rt!help captcha」と実行した際に表示される画像](/img/notes/help.png)
例として`captcha`コマンドのヘルプの画像を用意しました。  
`rt!help captcha`を実行すればDiscordでも閲覧が可能です。
### コマンドの引数について
そのコマンドが必要としてる情報を文字でコマンドの後ろに置くというものです。  
例えば「大好き！」か「大嫌い！」のどっちかを言ってもらうコマンド`rt!love`があったとします。  
この`rt!love`だけを実行してもRTは好き嫌いどっちを言えばいいかわかりません。  
そしてRTは`rt!love yesかno`のように`rt!love`の後ろに`yes`か`no`を置けば好き嫌いどっちを言うか決めれるようになりました。  
この`yes/no`の部分がコマンドの引数です。
#### コマンドの引数の見方
```markdown
**引数名** : どういう文字を渡せばいいか
引数の説明
```
のようにRTでは表記されます。  
`captcha`コマンドのヘルプの引数を例としてだします。(上の画像の引数です。)  
```markdown
**mode** : image,web,左の二つ以外の場合は合言葉
設定する認証の種類です。
`image`が画像認証で実行したチャンネルに送信される画像にある数字を正しく入力するという認証です。
`web`がhCaptchaを利用したウェブでの本格認証です。
上記二つ以外を入力した場合はその入力した言葉を使った合言葉認証で設定されます。
もし設定をオフにするならoffにして役職(role)を指定しないでください。

**role** : 役職名または役職のメンション,オプション
認証成功時に付与する役職の名前またはメンションです。
もし設定を解除する場合はこれを指定しないでください。
```
これをコマンド表記にすると以下のようになります。  
`rt!captcha <mode> <role:オプション>`  
後はわかりますね、RTのコマンドの引数はその名の通りそのコマンドの引数の説明をしています。

#### コマンドの引数に改行または空白がある際について
もし空白のある引数を入れたい場合は`"`でその引数を囲みましょう。  
そうしないと空白の次にある文字がその次の引数として使われてしまいます。  
例えば`危険 ミュート`ロールが付けられたら`メンバー`と言うロールを外すようにしようとコマンドを実行するとします。  
その時これを実行しました。`rt!linker link 危険 ミュート メンバー on`  
ですが思うように動きません。  
これは`危険 ミュート`で引数二つ分が使われてしまっているからです。  
なので`rt!linker link "危険 ミュート" メンバー on`としないといけません。  
ですがコマンドの最後の引数(次のひきすうが存在しない)な場合は`"`で挟まなくて良いです。

### エイリアスとは
たまにエイリアスというのがヘルプに出てくると思います。  
これはとても便利なものなので知っておいた方が良いです。  
ここでは`recruitment`という募集パネルを作るコマンドを例として説明します。  
今この`recruitment`というコマンドは長くて打つのめんどくさいですね。  
そういうめんどくさい人のためにRT開発者が用意したコマンドの言いかえがエイリアスです。  
`recruitment`のエイリアスは以下のようになっています。
```markdown
# エイリアス
recruit, rct
```
この場合`recruitment`は`rct`にしても実行できるということです。  
RTのコマンドはよく日本語のエイリアスもあるのでよくヘルプを見ればもっと簡単にコマンドが実行できるようになります。  
いいことを聞けましたねあなた！  

### 複数のコマンドが一つのヘルプにある件について
`tts`コマンドなどそうなっています。  
これは複数のコマンドがあるということではなくグループコマンドのサブコマンドがあるということです。
### グループコマンドとは
そのコマンドのまた下にコマンドがあるというものです。  
例えば読み上げのコマンドの`tts`の場合は読み上げ開始コマンドで`rt!tts join`というのがあります。  
そして切断のコマンドの`rt!tts leave`があります。  
また`rt!tts dictionary`の辞書コマンドもあります。  
そしてこの`dictionary`の下にも`add/remove`の辞書追加コマンドがあります。  
このように機能の複数のコマンドを一つのコマンドにまとめたものがグループコマンドです。  
サブコマンドはそのグループコマンドにあるコマンド一つ一つのことで`rt!tts join`の`join`にあたります。  
そういうグループコマンドの場合はそのコマンドのヘルプにそのコマンドのサブコマンドがすべて書いてあります。  
なので複数のコマンドが一つにあるわけではないです。

### RTのプリフィックスについて
プリフィックスというのはコマンド実行時にそのコマンドのあるBotのコマンドであるということがわかるようにコマンドを最初に書くものです。  
RTのプリフィックスは`rt!`となっています。  
実はこの`rt!`というプリフィックス以外にもRTを呼べるプリフィックスがあります。  
それは以下の通りです。
* rt!
* rt.
* りつ！ (このビックリマークは全角)
* りつ.

なので実行しようとしてるコマンドに日本語のエイリアスがあれば実行するコマンドを全て日本語にできたりします。