# いままでのまとめ

# **python**
まず初めに型の特性についての学習をした


# データ型	
**str**	文字列	文字、文字列
" " ダブルクォーテーション、もしくは' ' シングルクォーテーションで囲って定義する。	str = 'abc'
**int**
整数	小数点を含まない数値	num = 6
**list**（リスト型）
配列	1.複数の要素（文字列、整数、論理など）を含むもの。
2.[ ] を使って定義する。
3.格納した各要素の変更が可能。	list = ['abc', 6, True]
**tuple**（タプル型）	
タプル	1.複数の要素（文字列、整数、論理など）を含むもの。
2.( ) を使って定義する。
3.要素を追加・削除・変更できない	tuple = ('abc', 6, True)
**dictionary**（辞書型）
辞書	1.複数の要素（文字列、整数、論理など）を含むもの。
2.{ }を使って定義する。
3.キー値と合わせて値を設定することにより、キー値を元に値を参照できる。
4.格納した各要素の変更は可能。	dict = {'Key1' : 'Val1', 'Key2' : 'Val2'}
**set**　（集合型）
例えば　a=｛０，３，３，４，４，５，６｝と入力すると　a= {0,3,4,5,6,}
     が出力される。
　要するに重複しているものは一つだけ抽出される。
　重複した要素がない
　要素に順番がない
 
# **制御フロー**
 
**#  if文**
if 条件式1:
    `条件式1がTrueのときに行う処理`
elif 条件式2:
    `条件式1がFalseで条件式2がTrueのときに行う処理`
elif 条件式3:
    `条件式1, 2がFalseで条件式3がTrueのときに行う処理`
...
else:
    `すべての条件式がFalseのときに行う処理`
# 演算子	結果
|||
|-|-|
|x < y|xがyより小さければTrue|
|x <= y|xがyより小さいか等しければTrue|
|x > y|xがyより大きければTrue|
|x >= y|xがyより大きいか等しければTrue|
|x == y|xとyの値が等しければTrue|
|x != y	x|xとyの値が等しくなければTrue|
|x is y	x|xとyが同じオブジェクトであればTrue|
|x is not y|xとyが同じオブジェクトでなければTrue|
|x in y	x|がyに含まれていればTrue|
|x not in y|xがyに含まれていなければTrue|

  **for文**
基本的にこの書き方をする。
例　for 変数 in オブジェクト:
    実行する処理
range関数　繰り返し処理の回数を指定できる。
![](https://udemy.benesse.co.jp/wp-content/uploads/d62e9c9daad4e9bd365b343764da605a-large.png)
break
例　for num in range(20):
    print num
    if num == 10
        break
本来なら０から１９の数字がprintされるが０から１０の数字で処理が終わる。

**while文**

例文　while True :
    word=input('Enter')
    if word=='ok':
        break
    else:
        print("okをいれてください")　＃okという単語を入れると終了するプログラム

　　print("end")


*for文とwhile文の違い*
Pythonの繰り返し処理にはfor文というものもあります。 ではwhile文とfor文は何が違うのでしょうか？ 両者の違いは、ループの終了条件です。 for文：指定された回　　　数繰り返すと終了する while文：条件を満たさなくなったら終了する というように、while文は条件を満たすかどうかをループの基準にしており、条件がtrueの間は処理を繰り返し続けます。　（引用しました）
 


# その他（応用）
応用編で学習した項目はたくさんあります。
# class
**def** 
関数を定義、呼び出し。
例文　def ikko ():
    print("こんにちは")
ikko()　　# こんにちはが返ってくる
**init**
(コンストラクタ) は、インスタンスを生成したときに一度だけ呼び出されるメソッド。
基本的には対象のクラスのインスタンスを初期化するために利用する。。
**import**
「import」とは、Pythonでモジュールなどを利用するために使用するもの
例　import sqlite3
    import csv など

**ファイルへの読み込み　書き込み**

csvファイルからデータを読み込む
例文　with open('./file/lesson.csv','r',encoding='utf-8-sig') as csv_file:
    read=csv.DictReader(csv_file)
    l = []
    for row in read:
        row['合計']=int(row['国語'])+ int(row['数学'])+ int(row['社会'])
        print(row['seq'],row['name'],row['合計'])
        l.append({'seq':row['seq'],'name':row['name'],'合計':row['合計']})

csvファイルにデータを書き込む
例文　with open('./file/lesson 02.csv','w',encoding='utf-8',newline='') as csv_file:
    writer = csv.writer(csv_file)
    writer.writerow(['seq','name','合計'])
    for i in l:
        writer.writerow(list(i.values()))
        
# **データベース**

データベース(sql)専門学校で得た知識だけだったので、難しかったが、理解を深められたと思う。
||||
|-|-|-|
|データの検索| SELECT（データの検索）|SELECT 列名 FROM テーブル名 WHERE 条件式;
|データの追加| INSERT（データの追加）|INSERT INTO テーブル名 (列名, 列名, ...) VALUES (値, 値, ...);
|データの更新| UPDATE（データの更新）|UPDATE テーブル名 SET 列名 = 値 WHERE 条件式;
|データの削除| DELETE (データの削除)|DELETE FROM テーブル名 WHERE 条件式;
|テーブルの作成|　CREATE (テーブルの作成)|CREATE TABLE テーブル名 (列名 データ型, ...);
|テーブルの削除|　DROP (テーブルの削除)|DROP TABLE テーブル名
|テーブルの主キーの設定|　PRIMARY KEY(主キーの設定)|PRIMARY KEY (列名)

データベースの作成

sqlite3 ???.db（sqlite3の場合）

python上でデータベースを操作するうえでcursorを使用した。

例　sql=DROP TABLE ikko
    curs.execute(sql)

executeでは一行ずつで効率的な処理ではないのに対しfetchallは効率的に処理をしてくれる。
例
curs.execute('select * from table')
docs = curs.fetchall()
for doc in docs:
    print(doc)
   
   
# Githubについての纏め

gitで主に使用すると思われるコマンドをまとめました。
|||
|-|-|
|git init|デイレクトリにリポジトリを作成する。|
|git add [filename]|修正したファイルなどをインデックスに登録する。|
|git add .|上記の場合は指定のファイルのみ変更を登録するが、この場合全て登録する。|
|git status|前回のコミットと比較してどのファイルが変更されたかを確認できる。|
|git commit|addで操作したファイルをコミットしてくれる|
|git clone|github上にあるフォルダやファイルなどを引っ張ってこれる。|
|git push|ローカルリポジトリにコミットした内容をリモートリポジトリに送信する|
|git pull|クローンしたフォルダなどに新たな変更があった場合その変更を反映してくれる。|
|git fetch|変更したデータを取ってくる。反映はしてくれない。(確認だけしたい時などに使用する)|

![](https://backlog.com/ja/git-tutorial/assets/img/intro/intro4_1.png)

gitではワークツリ―からインデックスに一度登録をしてからリポジトリにいけるということを理解するのに時間がかかりました。
ですがgitを通して様々な知識を得られたと思います。

# **linux操作の纏め**

linux osとwindowsの違いを深く学べた。
windowsでは手の届かないこともlinuxでは操作できた。

linux のコマンド
|||
|-|-|
|cd|　ディレクトリ（フォルダ）移動 cd 移動したいフォルダ名|
|ls-al| フォルダの内容をリスト形式で表示する.中身をみたいフォルダに移動してから|
|mv| ファイルを移動 mv (移動元ファイル名/フォルダ名) (移動先ファイル名/フォルダ名)|　
|clear| 消さずに画面を綺麗にする|
|mkdir| フォルダを作成する　mkdir フォルダ名|
|touch| ファイルを作成する touch ファイル名|
|rm|　ファイルやフォルダを削除する　rm ファイル名/フォルダ名|
|pwd|　現在いる位置を表示する|
|cat| ファイルの内容を表示する cat ファイル名|

今後は課題でもあるlinucの資格を取得するためまだまだあるコマンドを覚えたいと思います。









