# unity_tcp-udp-receive-sample

Unity上でTCP/IPおよびUDP/IPのメッセージを受信するサンプルプログラムです。
TCP/IPやUDP/IPのメッセージを受信するたびに、キューブが回転します。

<img src="https://camo.githubusercontent.com/92bd0382f153eda05b8921a50a687325b292951b/687474703a2f2f73617a616d656b692e6a702f74656d702f756e6974795f7463702d7564702d726563656976652d73616d706c655f73637265656e73686f742e706e67" width="400px">

TCP/IPの受信コア部はTCPReceiver.cs、UDP/IPの受信コア部はUDPReceiver.csです。それぞれのスクリプトをEmpty Objectに追加し、ポート番号を変更することで、各種サーバを起動して利用できます。デフォルトのポート番号はそれぞれTCPが12345、UDPが22222に設定されていますが、Unityエディタのインスペクタから変更できます。

受信したメッセージの管理部分については、GameManager.csを参照してください。[MethodImpl(MethodImplOptions.Synchronized)] というアノテーションを使用した同期手法を使用して、メインスレッドとTCP/IPおよびUDP/IPの受信用スレッドの両方からメッセージ格納用のキューにアクセスしています。
