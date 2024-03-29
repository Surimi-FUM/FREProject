# FRE Project
博士研究テーマ  
釣り竿効果(Fishing Rod Effect)と呼ぶ錯覚を提唱し、それを実証すると共にVR向けインタフェースへの応用を目指す研究での成果物  

2022年開発  
https://user-images.githubusercontent.com/116449282/229968886-4ff7c06e-71f4-44c8-870a-cb9983bfc11a.mp4

2020年開発   
https://user-images.githubusercontent.com/116449282/229969163-7e8f4642-daf0-4f51-bad5-556606012812.mp4  

## FREdevice
作成したFRE装置に搭載されているサーボモータを制御する。  

## FREsystem
FRE装置をVRインタフェースとして活用するためのシステム。  
IMU(慣性計測ユニット)を使用して、FRE装置をコントローラとして扱えるようにする。  

## 概要  
研究で作成した実験装置をコントローラとしたVRアプリとその通信システムです。  
実験装置にはサーボモータとIMU(慣性計測機)が搭載されており、Raspberry Piを使用して値を読み取り、WebSocketサーバを介してVRアプリへ送信するシステムとなっています。  
実験装置に合わせてアプリを制作し、キャラクタにパンチをさせるアプリとモーションキャプチャによるオブジェクト操作アプリを作成しました。  

### 2022年  
Processingで開発。
マイコンをRaspberry Piに変更し、WebSocketサーバを介してデータ通信を行うシステムを構築した。  
研究室の仲間と協力して、ノイズフィルタを実装し、モーションキャプチャを実装した。  
軸ずれは完璧に抑えられなかったため、ボールの動く範囲を制限し、合成加速度が閾値を超えない動きは反映しないようにすることで、ずれを抑制する工夫をした。  

### 2020年  
Unityで開発。  
Arduinoとシリアル通信をして、IMUのセンサ値をアプリへ送信する。  
加速度センサの値が閾値を超えたとき、ユーザがパンチをしたと判定して、モデルのアニメーションを開始する。  
アニメーションが終わり切るまで次の動作を受け付けないようにして、誤作動を減らす工夫をした。  

## アピールポイント  
IMUを使用した姿勢・位置推定の実装が大変でした。  
センサには無視できないノイズと軸ずれがあり、それらをリアルタイムで修正するフィルタの実装がうまくいかずにいました。  
この問題を解決するため、教授から助言を受けたり、当時主催していた勉強会を通じて研究室の仲間に協力を仰ぎました。  
自分自身が書いたコードを整理して読んでもらうことで、記述ミスを発見し修正することができました。また、MATLABの機能を利用してシミュレーションを行い、適切なフィルタを特定する手助けをしてもらいました。  
さらに、周波数解析の方法を学び、フーリエ変換を使用して有効なカット周波数を特定することができました。  
彼らの協力により、センサの軌道を正確に捉えることができました。  
それでもリアルタイムフィルタでは、ジャイロドリフトやノイズを完全に修正することができなかったため、ソフトウェアの側で動きを反映させる球体の動く範囲を制限するなどの工夫を行いました。  
この経験により、データ解析の知識を得ることができ、自分自身の不足している部分をチームで補い合う意識を持つことができました。  

## 開発環境  
PC：Windows 10 Education、Intel Core i7-7700K  
メモリ：32.0GB  
GPU：NVIDIA GeForce GTX 1080  
IDE：PyCharm Professional、Processing4、Unity  
言語：Python3、C#  
フレームワークなど：WebSocket  

### テスト環境
PC：Windows 10 Pro、Intel Core i7-6700K  
メモリ：16.0GB  
GPU：NVIDIA GeForce GTX 1660 Ti  

## 開発期間・人数
令和2年(2019)/09 ~ 現在、1人
