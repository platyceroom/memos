# memos　（個別に渡すメモ）

XHR(ajax)のリクエスト先のPHPでこういう値を返すようにする
レスポンスはJSONになるので、javascriptでそのまま扱える

`'damage'` を上に `'text'`を右下にinnerHTMLで入れたらOK
```
$damage = 123; // randで計算したダメージ数値
$migi_shita_text = 'hogehogeに' . $damage .'を与えた'; //ダメージテキスト

$result = array(
  'damage'=> $damage, // ここは適当にダメージを
  'text' => $migi_shita_text // ここでテキストを代入
);

echo json_encode($result); // JSON形式にする
```

結果的に`{'damage':123,'text':'hogehogeに123を与えた'}`という文字列が`echo`で表示される

これが`req`に入るので、今の実装に書くとしたら
```
 // reqにはJSON文字列が入っているので、
 // JSで使えるようにオブジェクト化
parced_json =  JSON.parse(req);

ue = parced_json.damage // PHP側で$resultに入れた'damage'のことを指している
migi_shita = parced_json.text // PHP側で$resultに入れた'text'のことを指している
// あとはinnerHTMLするだけ
```



# ajaxで取得する値について

まずはAjaxで取得する対象の.phpでechoした場合どうなるか
echo した文字列がAjaxに入ってくるので、その点に気を付ける必要がある
```
<?php
echo 'hoge';
?>
```
このPHPの実行結果は
`hoge`

```
<?php
echo 'hoge';
echo 'fuga';
?>
```
このPHPの実行結果は
`hogefuga`

```
<?php
$arr = array('hoge', 'fuga');
$json = json_encode($arr);
echo json;
?>
```
このPHPの実行結果は
`['hoge',fuga]`

いずれの場合もAjaxで取得できる値はPHPの実行結果
さてJSで使いやすいのはどれだろうか


# ここまでの結果をjsで利用するためには

```
value = req.response
// ↑のPHPを使って仮にこうすると、valueの中身は'{[hoge, fuga]}'(String文字列)になる
parsed = JSON.parse(value);
// ↑の中身は['hoge', 'fuga'] (ちゃんとした配列)になる！
// parsed[0]を使うと'hoge'が取れる
// 連想配列も同じ
```

以上、野生のWebエンジニアより


## 番外
```
<?php
echo 'piyo';
$arr = array('hoge', 'fuga');
$json = json_encode($arr);
echo json;
?>
```
このPHPの実行結果は
`piyo['hoge',fuga]`
となるので、JSON形式が崩れて使えない！

↓私のDiscord
さらみたん#5566

