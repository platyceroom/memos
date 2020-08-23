# マスターデータを使ってみる

```
<?php

function calcSkill($skillMaster, $useSkill) {
  echo $skillMaster[$useSkill]['name'];
  echo $skillMaster[$useSkill]['death'] ? "即死":  "即死じゃない";

  // ダメージをdamageからとるか、個別に指定するか
  if ($skillMaster[$useSkill]['damageType'] === 'rand')
      echo "ランダムダメージ" . randomDamage(); // randとか使ってランダムダメージ出す関数を呼び出したり
  } else {
      echo "通常ダメージ" . $skillMaster[$useSkill]['damage'];
  }
}
// こういったマスターデータを用意することで管理が楽になる
$skillMaster = array(
    '001' => array(
      'name' => "殴る", // 技名
      'damage' => 10, // 技ダメージ
      'death' => false, // 即死
      'damage_type': 'normal', // ダメージ計算のパターン
      ),
    '002' => array(
      'name' => "蹴る",
      'damage' => 0,
      'death' => false,
      'damage_type': 'rand',  // ランダムダメージにしたいとき
      ),
    '003' => array(
      'name' => "飛び蹴り",
      'damage' => 0,
      'death' => true,
      'rand_damage': false,
      'damage_type': 'normal',
    )
    );

// 001などのスキルIDをどこかでまた管理しておき、使いたいIDを渡す
calcSkill($skillMaster, '001');


// ～慣れてきたら～
// $skillMasterはここで管理しつつHTMLにも同じく埋め込んでおくと
// 一元管理できるしAjaxで飛ばすIDも取れるよね。
```
