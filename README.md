# memos

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
