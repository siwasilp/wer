# プラグイン

3Dマップ上に付加的な情報を表示する、様々なプラグインが利用可能です。各プラグインが提供する情報はマップ上にレイヤーとして表示され、[レイヤー表示設定](./configuration.md#%E3%83%AC%E3%82%A4%E3%83%A4%E3%83%BC%E8%A1%A8%E7%A4%BA%E8%A8%AD%E5%AE%9A)パネルで表示のオン・オフを切り替えることができます。

## 降水プラグイン

<img :src="$withBase('/images/weather.jpg')" style="width: 580px;">

リアルタイムのレーダー情報をもとに、マップ上に雨の強度に応じた降水アニメーションを表示します。ズームレベルを上げていくと、より細かいメッシュの単位で降水の強弱が表示され、10分毎に最新の情報に更新されます。

詳細は [Mini Tokyo 3D 降水プラグイン GitHub レポジトリ](https://github.com/nagix/mt3d-plugin-precipitation)をご覧ください。

## 花火プラグイン

<img :src="$withBase('/images/fireworks.jpg')" style="width: 580px;">

マップ上に花火アニメーションを表示します。スケジュールされた日時に特定の場所の地図上で、花火打ち上げの3Dアニメーションを見ることができます。

詳細は [Mini Tokyo 3D 花火プラグイン GitHub レポジトリ](https://github.com/nagix/mt3d-plugin-fireworks)をご覧ください。

## ライブカメラプラグイン

<img :src="$withBase('/images/livecam.jpg')" style="width: 580px;">

東京近郊各地に配置されたライブカメラで、列車が走行する様子を見ることができます。地図上のライブカメラボタンをクリックまたはタップすると、その場所にズームインすると同時に、同じ視点から配信しているライブカメラ映像が表示されます。映像はリアルタイムで配信されていますが、数十秒程度の配信遅延があるため、地図上の列車の動きより若干遅れて実際の列車が映る傾向があります。ライブカメラボタンが存在しない地図上をクリックすると、ライブカメラの選択が解除されます。

詳細は [Mini Tokyo 3D ライブカメラプラグイン GitHub レポジトリ](https://github.com/nagix/mt3d-plugin-livecam)をご覧ください。

## PLATEAU プラグイン

<img :src="$withBase('/images/plateau.jpg')" style="width: 580px;">

[プロジェクト PLATEAU](https://www.mlit.go.jp/plateau/) が提供する東京の3D都市モデルを Mini Tokyo 3D と組み合わせて表示します。都心部では詳細な建築物の形状データとテクスチャーが利用できるため、非常にリアルな都市の景観を表示することができます。比較的大きな負荷がかかり、多くのメモリを要求するため、性能の高いデバイスでの使用を推奨します。

詳細は [Mini Tokyo 3D PLATEAU プラグイン GitHub レポジトリ](https://github.com/nagix/mt3d-plugin-plateau)をご覧ください。

## 東京2020オリンピックプラグイン

<img :src="$withBase('/images/olympics.jpg')" style="width: 580px;">

2021年7月23日〜8月8日開催の東京2020オリンピックの競技日程と会場についての情報を表示します。画面左上の時刻表示のすぐ下に、開催日前であれば開会式までのカウントダウン、開催期間中は現在何日目かの表示が出ます。また、地図上には競技会場の場所に競技のピクトグラムで表されるボタンが表示され、クリックまたはタップするとその場所にズームインして、その会場の競技日程の詳細が表示されます。さらに、国立競技場駅の付近には、東京2020オリンピックのために建築されたオリンピックスタジアムの精巧な3Dモデルが表示されます。

詳細は [Mini Tokyo 3D 東京2020オリンピックプラグイン GitHub レポジトリ](https://github.com/nagix/mt3d-plugin-olympics2020)をご覧ください。

::: warning 注意
東京2020オリンピックプラグインは、[https://minitokyo3d.com](https://minitokyo3d.com) では表示されません。[東京公共交通オープンデータチャレンジ向け Mini Tokyo 3D 2021](https://minitokyo3d.com/2021/)のページで見ることができます。
:::
