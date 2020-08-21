# クラスのインスタンス化に関して

```
<?php
// クラスのスコープ
class Enemy
{
    public $enemyName = ''; // 擬似変数

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
    /**
     * 擬似変数enemyNameにnamaeを入れつつ返す
     */
    public function setAndGetName($namae)
    {
        $this->enemyName = $namae;
        return $this->enemyName;
    }
}

$enemy1 = new Enemy(); // enemy 1
$enemy2 = new Enemy(); // enemy 2

// 何もせずEnemyの擬似変数enemyNameを取ってみる
echo $enemy1->enemyName; // 空文字

// 擬似変数にセットしてみる
$enemy1->setName('ゴブリン'); // ゴブリンを擬似変数enemyNameに入れる
echo $enemy1->setName('ゴブリン'); // 上と同じ、だがreturnがないのでecho nullと同じ

// 擬似変数から値を取り出してみる
echo $enemy1->enemyName; // ゴブリン

// セットしつつ返すやつ
echo $enemy1->setAndGetName("オーガ"); //結果は オーガ
echo $enemy1->enemyName; // オーガ    



// ------------------------------------------------
// ここからはインスタンス化されたenemy2の中身を見る
echo $enemy2->enemyName; // 空文字
// enemy1とは別インスタンスとして変数に初期化されているのでこっちはなにもはいっていない

```
