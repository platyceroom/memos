# スコープに関して

```
<?php
// スコープ
// エラーになる部分はコメントアウトして動かしてね

if (false) {
    $a = 'a';
}
echo $a; // エラー

function hoge()
{
    $b = 'b';
}
echo $b; // エラー


$c = '';
function fuga()
{
    $c = 'c';
}

echo $c; // 空
?>
```

```
<?php
// クラスのスコープ
// エラーになる部分はコメントアウトして動かしてね
class Hoge
{
    public function a()
    {
        echo 'a';
    }
    public function b()
    {
        echo 'b';
        $this->a();
        $this->c();
    }
    private function c()
    {
        echo 'c';
    }
}

    $hoge = new Hoge(); // Hogeをインスタンス化

    echo $hoge->a(); // a
    echo $hoge->b(); // b a c
    echo $hoge->c(); // エラー
?>
```
