# Tel-SMS-repsonder
Twilio電話番号に着信があったときに、発信者にSMSを送り返すPHPスクリプトです。

050の番号に電話を掛けるだけで URL をSMSで通知できます。
今までのQRコードを電話番号に置き換えることが可能です。

##利用イメージ
1.利用者がTwilioの日本の番号(050/0120/0800)に携帯電話から発信
2.アナウンスが流れたあと電話が切断
3.発信者の番号にSMSが送信される。中にURLが記載されている

##セットアップ手順
  1.Twilioのアカウントをサインアップ・取得(http://twilio.kddi-web.com/）
  2.クレジットカードでポイントを購入(最低2000円から)
  3.Twilioの日本の番号(050/0120/0800)とアメリカの番号(+1)の番号を購入
  4.スクリプト中の以下の部分を修正
    18-22行目 携帯電話からかかってきた時のアナウンス を変更
    23行目 +1XXXXXXXXXX を取得したアメリカ番号に変更
    24行目 「URLをお送りしております。 twilio.kddi-web.com」をお好きな文に変更
            http/s をつけるとauに送信の際弾かれます。文字数制限にご注意ください
    31-34行目 「携帯電話以外からかかってきた時のアナウンス」 を変更
  5.PHPの利用できるサーバー・PaaS上にスクリプトを設置
  6.日本の番号(050/0120/0800)番号の「RequestURL」にファイルのURLを設定
  7.完了

##役に立つリソース
-Twilio for KDDI Web Communications SMS および 注意事項
http://twilio.kddi-web.com/function/sms/

- Twilio は連結 SMS メッセージや 160 文字以上のメッセージをサポートしますか?
https://twilioforkwc.zendesk.com/entries/24268516-Twilio-%E3%81%AF%E9%80%A3%E7%B5%90-SMS-%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%84-160-%E6%96%87%E5%AD%97%E4%BB%A5%E4%B8%8A%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B-

- 発信通話と SMS メッセージの 1 秒当たりの発信制限は何件ですか ?
https://twilioforkwc.zendesk.com/entries/23571982-%E7%99%BA%E4%BF%A1%E9%80%9A%E8%A9%B1%E3%81%A8-SMS-%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%81%AE-1-%E7%A7%92%E5%BD%93%E3%81%9F%E3%82%8A%E3%81%AE%E7%99%BA%E4%BF%A1%E5%88%B6%E9%99%90%E3%81%AF%E4%BD%95%E4%BB%B6%E3%81%A7%E3%81%99%E3%81%8B-
