# 概要  
2022年7月18日に参加したCTFコンテスト(https://ctf.nazotoki.tech) の記録です。  
解答・解き方は▶をクリックして開くと読めます。  
解いた部分はほぼノーコードで解けました。  

# お品書き  
## Congratulations!!  
- <details><summary>　【未回答】Thank you (201) </summary></details>  
  
## Last Challenge  
- <details><summary> 【未回答】最終問題 (200) </summary></details>  
  
## 2nd Challenge  
- <details><summary> 【未回答】へびつかい座 (100) </summary></details>  
  
## Misc - Water elements  
<details>
　　<summary> 【未回答】かに座 (14) </summary>
    「cancer.zip」がある。とりあえず展開してみる。32文字の文字列が13個表示される。  
    4de447a391e32baeb5a52c55aa14467b  
    7c70e2cb2b4a13c4590f6b15c30385fd  
    44ca0844398b2d010d8cd4a31ddb023d  
    397cbf6db9d7ae6906ae420aedc5346c  
    550eadb88a230018bf043d1b6ad15863  
    635cbc8a5dc1a528c3b5cb9eecdc1086  
    766cc4dd4d5005652e8514e3513683f8   
    0961db32a59b8a83c1996498f9d1d80e  
    7463543d784aa59ca86359a50ef58c8e  
    a0678bcea04dbd6852c219062ab2bb3c  
    b9c94e8a87e3647c5a0fa4ff358ecc65  
    f8a5c386478fa64f118056b82acc31d2  
    f0525aafa095ed2665d03681537a70ea  
  
    (13って怪しくない？)  
    32文字なので16進数やURLエンコードを疑ってみる。  
</details>  

<details>  
    <summary> さそり座 (24)  </summary>  
    犬とってもかわいい！！ダックスかな。
    ヒント使用。おめめを拡大してみよう。  
    > 答え
    ``` 
    カクダイ
    ```  
</details>  

<details>
    <summary> 【未回答】うお座 (34) </summary>  
    「みずがめ座からてんびん座に向かうとき、ひみつの鍵が手に入るだろう。水の中に浮かぶ真実を見定めよ。」  
    パスワードがかかっていて展開できない。  
    ヒント1　ヘッダーの仕様を示唆。  
    ヒント2「リファラーの情報にaquariusが含まれた状態でてんびん座のサイトにアクセスすると鍵が手に入りそうです。書き換えられないでしょうか？ やり方がわからない人は「リファラー 書き換え」とかでぐぐると良いかもしれません。」  
    > 答え
    ``` 
    ```
</details>  


## Web - Air elements  
<details>  
    <summary> ふたご座 (13) </summary>  
    ヒント見ました  
    webページにアクセスすると、「パスワードはdioskouroiってわかってるはずなんだけど...」と出る。  
    開発者ツールのhtmlを書き換えればいいとのこと  
    開発者ツールを開いてみると、  
    <input type="hidden" name="realPassword" value="dummyPassword">となっており、このままでは何を入力しても  
    「dummyPassword」が入力値として送信されてしまう。  
    該当部分をダブルクリックすると(筆者はGoogleChromeを使用)編集ができるので、  
    value="dioskouroi"に書き換えてsubmitする。  
    
    すると遷移先ページで  
    "🦗 < 解いてくれてありがとう！フラグをどうぞ！nazotokiCTF{ナイーブ}"と表示される。  
    > 答え  
    ```  
    ナイーブ  
    ```  
</details>  
     
<details>
    <summary> てんびん座 (23) </summary>
    時間切れ。
    「stardustChrome」なる聞いたことないブラウザを要求された。
    使っているブラウザの情報はヘッダー情報の`user-agent`内にあるため、UserAgentを偽装するといいらしい。
    「ネットワーク状態」から「[]ブラウザのデフォルトを使用」のチェックを外し、
    カスタム欄に「stardustChrome」と入力してページを再読み込みした。
    参考：(https://aprico-media.com/posts/1579)

    遷移先ページで  
    "確かにstardustChromeを使ってるね。フラグをどうぞ！nazotokiCTF{クローン}"と表示される。  
    > 答え  
    ```  
    クローン  
    ```  
</details>  

<details>
    <summary> みずがめ座 (33) </summary>
    ヒント1より「入社番号を一人だけ知っている人」＝99番のアイちゃん、passwordで検索する
    (好きなもの：まゆげみたいな模様のある犬。かわいい。)
    フラグのヒントはナンバー9999に載せておいたよ！入社前情報だから普通のパスワードでは見れないかもね。

    ヒント3より「パスワード入力フォームにSQLインジェクションの脆弱性があります。社員ナンバー：9999 か 99
    パスワード：' or 1=1 ;と入力してみてください。」

    入社試験受けてる君の情報入ってるのを発見。名前「なんだっけ」ｗｗ
    メモnazotokiCTF｛この候補者の名前｝
    > 答え
    ``` 
    タカハシ
    ```
</details>  

## Knowledge - Earth elements  
<details>  
    <summary> おうし座 (12) </summary>  
    2021年に行われた、コンピューターウイルス「emotet」のテイクダウン作戦  
    = Operation LadyBird  
    =「○○○○ムシ作戦」  
    参考：(https://xtech.nikkei.com/atcl/nxt/mag/nnw/18/041800012/042100139/)  
    
    
    検索時のポイント  
    「emotet 作戦」で検索。  
    「emotet テイクダウン」だとemotet対応済のプレスリリース等が多くヒットして見つかりにくいし、  
    「emotet　対策」だとセキュリティソフトの広告が多く引っかかる。  
    
    > 答え  
    ```  
    テントウ  
    ```  
</details>
  
<details>
    <summary> おとめ座 (22) </summary>
    「Webアプリケーションのセキュリティ分野の研究・ガイドラインの作成・脆弱性診断ツールの開発・イベント開催などの活動をしているオープンソースソフトウェアコミュニティの名称の読み方をカタカナ4文字で答えよ。」
    OWASP(https://owasp.org/www-chapter-japan/)
    学生会員は年20ドルからとのこと。

    > 答え
    ```
    オワスプ
    ```
</details>  

<details>
    <summary> やぎ座 (32) </summary>
    logを日本語で何というか？＝対数。　一瞬「指数かな？」と思ってあせった。
    > 答え
    ```
    タイスウ
    ```
</details>  

## Riddle - Fire elements  
<details>   
    <summary> おひつじ座 (11) </summary>  
    あなたが目指しているもの＝セキュリティエンジニアの「星」
    プロローグ(https://ctf.nazotoki.tech/prologue)のアイちゃんのメッセージの「★イントロダクション🌸」から
    「★がんばってネ!おうえんしてルよ!☺」の★の行を縦読みすると答え。
    > 答え
    ```
    ハンドル
    ```
</details>  


<details>
    <summary> しし座 (21) </summary>
    「leo.png」をダウンロードする。
    ルール(https://ctf.nazotoki.tech/regulation)に、「大切なルール　燃えるゴミは捨ててください　ペットボトル」
    とあるので、カタカナの「モエルゴミ」と「ペットボトル」を消す。
    > 答え
    ```
    チーター
    ```
</details>  

<details>
    <summary> いて座 (31) </summary>
    これもヒント見ました。東西南北＝イースト、ウエスト、サウス、ノース。
    「sagittarius2.png」って怪しくない？なんで2？
    > 答え
    ```
    イースト
    ```
    </details>  

## Tutorial
<details>
    <summary>　Welcome (1) </summary>
    練習。
    > 答え
    ```
    ナゾトキ
    ```
</details>  


<details>
    <summary>TODO </summary>
    ・GitHubの確認
    ・.encファイルを見るためにファイル暗号化ソフト「ED」を使う。
    ・かに座の暗号を解く
</details>  