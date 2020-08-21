# コンストラクタについて

先にインスタンス化の方を見ておこう

```
<?php
// クラスのスコープ
class Enemy
{
    public $enemyName = ''; // 擬似変数

    /**
     * コンストラクタ
     * インスタンス化された最初に呼び出される
     */
    public function __construct($namae)
    {
        $this->enemyName = $namae;
    }
    /**
     * 渡されたnamaeを擬似変数enemyNameに入れる
     */
    public function setName($namae)
    {
        $this->enemyName = $namae;
    }
    /**
     * 擬似変数enemyNameの中身を返す
     */
    public function getName()
    {
        return $this->enemyName;
    }
}

    $enemy = new Enemy('ゴブリン'); // この時点でconstructerが動く

    // 何もせずEnemyの擬似変数enemyNameを取ってみる
    echo $enemy->enemyName; // ゴブリン

    // 擬似変数にセットしてみる
    $enemy->setName('オーガ'); // オーガを擬似変数enemyNameに入れる

    // 擬似変数から値を取り出してみる
    echo $enemy->enemyName; // オーガ
```
