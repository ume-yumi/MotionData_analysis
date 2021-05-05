# MotionData_analysis

#### 実験状況
*脳への磁気刺激（TMS）の前後で、左手・左足の周期運動のパフォーマンスの変化を評価。
*モーションキャプチャ（LIBERTY, polhemus）のセンサを、手首・足首に一つずつ取り付け、時系列の角度変化を計測
※[LIBERTY ホームページ](https://polhemus.com/motion-tracking/all-trackers/liberty)
#### 計測タイミングは、刺激前に３回（pre1、pre2、pre3）、刺激後一定の時間間隔ごとに９回（0min, 5min, 10min, 20min, 30min, 40min, 50min, 60min, 90min）
#### センサ二つ分のローデータから、データのソーティング、Z軸周りの回転角の抽出、二つのセンサの相対位相を算出する

# Inputデータの説明
#### X座標、Y座標、Z座標、回転角度（X）、回転角度（Y）、回転角度（Z）がセンサ1とセンサ2で【交互に】並んでいる。


# Outputデータの説明
### sortファイル：
#### ローデータをセンサ1とセンサ2で分け、Z軸周りの時系列の回転角度を抽出。サンプリングレート（240Hz）を考慮した時間経過の列も挿入。
### peakファイル：
#### sortファイルより、手首・足首の伸展ピーク時間を抽出
### AEファイル：
#### peakファイルより、手首・足首の周期運動の位相が、ターゲット（180度）からどの程度ずれていたかを計算。
### rythmファイル：
#### peakファイルより、手首・足首の周期運動の周期が、ターゲット（1～2.5Hzまで、被験者によって一定）からどの程度ずれていたかを計算。
