# EMUZ80-68030
32bit  
PERSONAL WORKSTATION

![MEZ68030](https://github.com/satoshiokue/EMUZ80-68030/blob/main/imgs/IMG_1812.jpeg)  
MC68EC030  

![MEZ68030Socket](https://github.com/satoshiokue/EMUZ80-68030/blob/main/imgs/MEZ68030_socket.jpg)  
ICソケットの例  

電脳伝説さん(@vintagechips)のEMUZ80が出力するZ80 CPU信号をメザニンボードで組み替え、MC68030を動作させることができます。  
MC68EC030RP25B8P10とPIC18F47Q43の組み合わせで動作確認しています。  

動作確認で使用したMPU  
MC68EC030RP25B  
MC68EC030RP40B  
MC68030RC33C

ソースコードはGazelleさんのEMUZ80用main_cpz.cを元に改変してGPLライセンスに基づいて公開するものです。

https://drive.google.com/drive/folders/1NaIIpzsUY3lptekcrJjwyvWTBNHIjUf1

## メザニンボード
https://github.com/satoshiokue/MEZ68030

## 回路図
https://github.com/satoshiokue/MEZ68030/blob/main/MEZ68030.pdf

## ファームウェア
EMUZ80で配布されているフォルダemuz80.X下のmain.cと置き換えて使用してください。  
ターゲットのPICを適切に変更してビルドしてください。  


## アドレスマップ
```
ROM   0x0000 - 0x3FFF 16Kbytes
RAM   0x8000 - 0x8FFF 4Kbytes (0x9FFF 16Kbytes:PIC18F47Q84,PIC18F47Q83)

UART  0xE000   Data REGISTER
      0xE001   Control REGISTER
```

## PICプログラムの書き込み
EMUZ80技術資料8ページにしたがってPICに適合するemuz80_68030_Qxx.hexファイルを書き込んでください。  
"Enhanced 68k BASIC Version 3.54"が起動します。

## 68030プログラムの改編
バイナリデータをテキストデータ化してファームウェアの配列rom[]に格納するとMC68030で実行できます。

テキスト変換例
```
xxd -i -c16 foo.bin > foo.txt
```

### EhBASIC68k for EMU
https://github.com/satoshiokue/EhBASIC68k-EMU

## 謝辞
思い入れのあるMPUを動かすことのできるシンプルで美しいEMUZ80を開発された電脳伝説さんに感謝いたします。

このコンセプトに触れたことで手にできなかったX68030への想いをMEZ68030で叶えることができました。

"POWER TO MAKE YOUR DREAM COME TRUE"

## 参考）EMUZ80
EUMZ80はZ80CPUとPIC18F47Q43のDIP40ピンIC2つで構成されるシンプルなコンピュータです。

![EMUZ80](https://github.com/satoshiokue/EMUZ80-6502/blob/main/imgs/IMG_Z80.jpeg)

電脳伝説 - EMUZ80が完成  
https://vintagechips.wordpress.com/2022/03/05/emuz80_reference  
EMUZ80専用プリント基板 - オレンジピコショップ  
https://store.shopping.yahoo.co.jp/orangepicoshop/pico-a-051.html

## 参考）phemu6809
comonekoさん(@comoneko)さんがEMUZ80にMC6809を搭載できるようにする変換基板とファームウェアphemu6809を発表されました。

![phemu6809](https://github.com/satoshiokue/EMUZ80-6502/blob/main/imgs/IMG_6809.jpeg)

https://github.com/comoneko-nyaa/phemu6809conversionPCB  
phemu6809専用プリント基板 - オレンジピコショップ  
https://store.shopping.yahoo.co.jp/orangepicoshop/pico-a-056.html

