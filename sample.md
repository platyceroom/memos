# マスターデータを使ってみる

```
<?php

function calcSkill($skillMaster, $useSkill) {
  echo $skillMaster[$useSkill]['name'];
  echo $skillMaster[$useSkill]['damage'];
}

$skillMaster = array(
    '001' => array(
      'name' => "殴る",
      'damage' => 10,
      ),
    '002' => array(
      'name' => "蹴る",
      'damage' => 20,
      )
    );


calcSkill($skillMaster, '001');
```
