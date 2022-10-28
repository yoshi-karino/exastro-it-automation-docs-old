


|条件式|ルール名|アクション|条件回数|条件期間|親グループ|優先順位|小グループ|優先順位|
|----|----|----|----|----|----|----|----|----|
|Msg1|ルール1|なし|2|600|グループA|1|グループA1|1|
|Msg2|ルール2|自動対処|3|600|グループA|2|グループA1|2|


```puml

	
@startuml
<style>
timingDiagram {
 constraintArrow {
  LineColor Blue
    FontColor Blue
 }
}
</style>

scale 100 as 100 pixels
robust "アクション" as ACT
robust "グループ内条件" as CON
robust "ルール1 条件回数" as rule1
robust "ルール2 条件回数" as rule2
concise "取得メッセージ" as MSG
' hide time-axis

CON@0 <-> @+101 : Msg1 発生待ち
CON@100 <-> @+251 : ルール1 or 2条件達成待ち
CON@350 <-> @+151 : ルール2条件達成待ち
CON@500 <-> @+200 : 条件期間経過待ち
CON@700 <-> @+200 : Msg1 発生待ち

ACT has 実行,未実行
CON has ルール2条件達成,ルール1条件達成,コリレーション分析中,未評価
rule1 has 2,1,0
rule2 has 3,2,1,0

@0
ACT is 未実行
CON is 未評価
rule1 is 0
rule2 is 0
MSG is Msg2 #pink
@+50
MSG is {hidden}

@+25
MSG is Msg1
@+25
rule1 is 1
CON is コリレーション分析中
MSG -> rule1 : \nコリレーション開始メッセージ発生\n条件回数 +1
rule1 -> CON : \nコリレーション分析開始
@+25
MSG is {hidden}

@+50
MSG is Msg2 #pink
@+25
MSG -> rule2 : 条件回数 +1
rule2 is 1
@+25
MSG is {hidden}

@+100
MSG is Msg1
@+25
MSG -> rule1 : 条件回数 +1
rule1 -> CON : ルール1条件達成
CON is ルール1条件達成
rule1 is 2

@+25
MSG is Msg2 #pink
@+25
rule2 is 2
MSG -> rule2 : 条件回数 +1
@+25
MSG is {hidden}

@+50
MSG is Msg2 #pink
@+25
CON is ルール2条件達成
rule2 is 3
MSG -> rule2 : 条件回数 +1
rule2 -> CON : ルール2条件達成
@+25
MSG is {hidden}

@+75
MSG is Msg1
@+50
MSG is {hidden}

@+50
ACT is 実行
CON -> ACT : \nアクション実行条件を全て達成
CON is 未評価
rule1 is 0
rule2 is 0

@+100

highlight 95 to 695 #Lightyellow;line:DimGrey : 条件期間(600s)


@enduml

```

|条件式|ルール名|アクション|条件回数|条件期間|親グループ|優先順位|小グループ|優先順位|
|----|----|----|----|----|----|----|----|----|
|Msg1|ルール1|なし|2|300|グループA|1|グループA1|1|
|Msg2|ルール2|自動対処|3|300|グループA|2|グループA1|2|

```puml

	
@startuml
<style>
timingDiagram {
 constraintArrow {
  LineColor Blue
    FontColor Blue
 }
}
</style>

scale 100 as 100 pixels
robust "アクション" as ACT
robust "グループ内条件" as CON
robust "ルール1 条件回数" as rule1
robust "ルール2 条件回数" as rule2
concise "取得メッセージ" as MSG
' hide time-axis

CON@0 <-> @+101 : Msg1 発生待ち
CON@100 <-> @+251 : ルール1 or 2条件達成待ち
CON@350 <-> @+51 : ルール2条件達成待ち
CON@410 <-> @+216 : Msg1 発生待ち
CON@625 <-> @+275 : ルール1 or 2条件達成待ち

ACT has 実行,未実行
CON has ルール2条件達成,ルール1条件達成,コリレーション分析中,未評価
rule1 has 2,1,0
rule2 has 3,2,1,0

@0
ACT is 未実行
CON is 未評価
rule1 is 0
rule2 is 0
MSG is Msg2 #pink
@+50
MSG is {hidden}

@+25
MSG is Msg1
@+25
rule1 is 1
CON is コリレーション分析中
MSG -> rule1 : \nコリレーション開始メッセージ発生\n条件回数 +1
rule1 -> CON : \nコリレーション分析開始
@+25
MSG is {hidden}

@+50
MSG is Msg2 #pink
@+25
MSG -> rule2 : 条件回数 +1
rule2 is 1
@+25
MSG is {hidden}

@+100
MSG is Msg1
@+25
MSG -> rule1 : 条件回数 +1
rule1 -> CON : ルール1条件達成
CON is ルール1条件達成
rule1 is 2

@+25
MSG is Msg2 #pink
@+25
rule2 is 2
MSG -> rule2 : 条件回数 +1

@+10
CON is 未評価
rule1 is 0
rule2 is 0
@+15
MSG is {hidden}

@+50
MSG is Msg2 #pink
@+50
MSG is {hidden}

@+75
MSG is Msg1
@+25
rule1 is 1
CON is コリレーション分析中
MSG -> rule1 : \nコリレーション開始メッセージ発生\n条件回数 +1
rule1 -> CON : \nコリレーション分析開始
@+25
MSG is {hidden}

@+150

highlight 95 to 405 #Lightyellow;line:DimGrey : 条件期間(300s)
highlight 620 to 900 #Lightyellow;line:DimGrey : 条件期間(300s)

@enduml

```