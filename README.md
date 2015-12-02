# tama-bio
多摩市生物多様性WG（仮称）用Webサイト開発のためのリポジトリ。

# 日射量と川との距離のラスター計算機
- 日射量の最小最大
  - 750-7576.6
- 偏差からの範囲
  - 最小4735.06-7285.24
- irra(4735-7285):7285を100
- kasen_dist(0-100):0を100
- 日射量を0-100に変換
```
("Global (total) irradiance/irradiation [Wh.m-2.day-1]@1">4735)*(("Global (total) irradiance/irradiation [Wh.m-2.day-1]@1"-4735)*100/(7285-4735))
```
- 川からの距離
```
("kasen_distance@1"<100)*(100-"kasen_distance@1")
```
- 合成
```
((("Global (total) irradiance/irradiation [Wh.m-2.day-1]@1">4735)*(("Global (total) irradiance/irradiation [Wh.m-2.day-1]@1"-4735)*100/(7285-4735)))
*
(("kasen_distance@1"<100)*(100-"kasen_distance@1"))
)^0.5
```

