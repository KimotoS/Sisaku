# スマホとラズベリーパイをBlynkというアプリで連携してラズベリーパイで得た温度、湿度、気圧のデータをPCに表示する。
スマホ操作で温度、湿度、気圧のデータをラズベリーパイで取得してPCに表示するシステムを作ろうと思います。


https://rcmdnk.com/blog/2019/08/18/computer-iot-raspberrypi/
<br>
このサイトを見ながら設定をしてラズベリーパイの方でmain.cppを開き下の部分に変更します。
<br>
BLYNK_WRITE(V1)
<br>
{
<br>
&emsp;printf("Got a value for V%d: %s\n", V1, param[0].asStr());
<br>
&emsp;if(param[0].asInt() == 1){
<br>
&emsp;&emsp;system("sudo python3 ★/home/pi/python-host/switchbot_py3.py★");//星で囲んだ部分は環境取得プログラムのパスを入れてください。
<br>
&emsp;}
<br>
}
<br>
以上の作業をすることによってスマホのアプリのボタンを押すと自動で温度、湿度、気圧を取得してくれます。
<br>
環境データ取得プログラム

<br>
参考にしたサイト
<br>
https://www.souichi.club/m5stickc/m5stickc-ble/ & https://rcmdnk.com/blog/2019/08/18/computer-iot-raspberrypi/
