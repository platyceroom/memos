# マスターデータを使ってみる

```
<?php

function calcSkill($skillMaster, $useSkill) {
  echo $skillMaster[$useSkill]['name'];
  echo $skillMaster[$useSkill]['damage'];
  echo $skillMaster[$useSkill]['death'] ? "即死":  "即死じゃない";
}
// こういったマスターデータを用意することで管理が楽になる
$skillMaster = array(
    '001' => array(
      'name' => "殴る", // 技名
      'damage' => 10, // 技ダメージ
      'death' => false, // 即死
      ),
    '002' => array(
      'name' => "蹴る",
      'damage' => 20,
      'death' => false,
      ),
    '003' => array(
      'name' => "飛び蹴り",
      'damage' => 0,
      'death' => true,
      )
    );

// 001などのスキルIDをどこかでまた管理しておき、使いたいIDを渡す
calcSkill($skillMaster, '001');
```
