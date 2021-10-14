udpled
======
The 納屋用です。

udpled は、[Arduino](https://ja.wikipedia.org/wiki/Arduino#Arduino_IDE) IDE を用いて開発、コンパイル、マイクロコントローラへの書き込みを行うことを想定した Sketch です。
[ESP32](https://ja.wikipedia.org/wiki/ESP32) 用にコンパイルし、 ESP32 に書き込みを行うことを想定していますが、他のネットワーク機能を有し、 Arduino と互換性があるマイクロコントローラでも大きな変更なく動く可能性が高いです。

実行の確認には、[ＷｉＦｉモジュール　ＥＳＰ－ＷＲＯＯＭ－３２Ｄ](https://akizukidenshi.com/catalog/g/gM-13318/)を用いています。

# 動作概要
udptape は、起動すると dhcp で自身の IP アドレスを自動取得します。mDNS を用いており、自動取得した IP アドレスは "udpled_0001.local" への問い合わせで解決することができます。
udptape は、 8888/udp で通信を待ち受け、受け取ったデータを SPI に変換し、12 番ピンに出力します。
