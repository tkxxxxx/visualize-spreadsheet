# visualize-spredsheet

Google Apps Script　でやると
構成
GAS + Google Charts API ( timeline )

source
https://script.google.com/a/g.softbank.co.jp/d/1H1dyHlPZHWEenOoYnleisuK16Jm93_8BpXCcQryg3S1o8x5umACIQzdH/edit

## memo
そこそこできるが、ほぼjava scriptでの処理。
google apps script 経由でのサーブになるので、iframe化されているところが扱いにくい。
脱GAS でやると
構成
js + Google App Engin + Gooogle Chart API

source
timeline.html

変わった部分
自動的に更新されるようにした。
ステータスを文字として表示させた。
## memo
GAE出なくてもホスティングできるが、名前解決出来る必要があるので GAEでstatic web hosting する。
認証は、googleでログインのjavascript版でやる。 access_tokenを使ってデータを持ってくる。
GAEは https onlyに設定。
spread sheetからデータを持ってくる処理は tq https://developers.google.com/chart/interactive/docs/spreadsheets
tq で必要な権限は drive の read only でok。　# spreadsheetのrw OK。　ro NG.
自動更新は RefreshIntervalに任せる。
現在時刻の縦線は、強引にsvgに書き込む。
## issues
