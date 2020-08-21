# memos　（個別に渡すメモ）

### 話しながら伝えるために書いたメモ
```
<?php
// クラスのスコープ
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

    $hoge = new Hoge();

    echo $hoge->a(); // a
    echo $hoge->b(); // b a c
    echo $hoge->c(); // エラー
?>
```

```
<?php
// functionのスコープ

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
