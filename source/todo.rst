ToDO
###############################################################################

tracing jitはじめて。 method jit以外の制御を追いたい。
-------------------------------------------------------------------------------
tracing jitといえば、spider monkeyがメジャーかな。

dalvik vmのjitはtracing jitがメインみたい。

JITのコンパイラの最終結果がどんなARMのAsmに落ちるんか、適当にpretty printするか
-------------------------------------------------------------------------------
オプションは見つけたけど、有効にする方法がわからないので、

適当にsrcを修正して試してみる。

ARMアセンブラ勉強しよう
-------------------------------------------------------------------------------

JITコンパイルした出力をみてみる。

androidのビルドしてエミュレータを弄ってみよう。
-------------------------------------------------------------------------------
x86だとビルド出来なかったけど、VMwareいれてx64環境でビルド

corei7 mem3.xG メモリがそろそろ限界... Haswellでたらx64にしてメモリ沢山つもう。。

trunkのチェックアウトの度にビルドに必要なメモリが増えているような、、

中間表現のMIRとLIRのデザイン 適当にpretty printするか。
-------------------------------------------------------------------------------

基本的には、既存のdexの情報を解析して、dexより上位のMIRを作っているぽい。

また、dexから機種依存のLIRを生成しており、そのLIRはほぼアセンブラと等価なはず。

LIRは、アーキテクチャごとに定義されており、ARMLIRの動作を追った。


自分のandroidスマホにJITコンパイルしたARMアセンブラをログ出力させたい。
-------------------------------------------------------------------------------

dalvikvmの起動オプションなんぞは、runなんちゃらに記述されており、

一般的にカスタムロムを生成する必要があるらしい。

気軽には変更できないとのこと。。。

/sdcard/cfg/にログを出力する方法
-------------------------------------------------------------------------------
まずはマウントする必要がある？

sdcardのイメージを生成したのち、マウントするらしい。

/sdcardにdotを出力するようにpretty printが設定されている。

他の場所に吐いて問題ないのでしょうかね。。


