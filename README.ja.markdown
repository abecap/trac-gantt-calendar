
TODO
------

* IEだとガントチャートのチケットがポップアップされない
* マイルストーンの期日ラインがあればいいな(DONE)
* trac-admin upgradeで自動的に設定
* eggのバグ?
* 担当のチケットの所でCCに自分の名前があるチケットも入れたい
* 開始日/終了日がないチケット→イベント扱い?


[説明
-----
カレンダーを表示するプラグインです。Trac 0.11に対応しています。Trac 0.10
以前のバージョンでは残念ながら動作しませんので、注意してください。

インストール
--------
> python setup.py bdist_egg
でeggファイルを作成し、dist/TracTicketCalendarXXX.eggをTracのpluginsディ
レクトリへコピーしてください。

使い方
-----
インストールすると、TracにCalendarメニューが表示され、ここをクリックする
だけでCalendarが利用できるようになります。TicketCalendarプラグインは、カスタム
フィールドのdue_assignとdue_close調べて、ticketを表示します。trac.iniに次
のように設定しておくと良いでしょう。

```python
  [ticket-custom]
  due_assign = text
  due_assign.label = 開始日
  due_assign.order = 1
  
  due_close= text
  due_close.label = 終了日
  due_close.order = 2

  complete= text
  complete.label = 進捗率(%)
  complete.order = 3
```

カスタムフィールドの開始日と終了日は、YYYY/MM/DDの形式で入力します。例えば、
2007/01/31などと記述します。


