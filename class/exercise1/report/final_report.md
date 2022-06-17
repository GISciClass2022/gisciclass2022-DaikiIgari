---
title: "観光客数と製造品出荷額の関係"
author: "猪狩 大気"
date: "2022/6/17"
output:
  html_document:
    df_print: paged
    theme: flatly
    toc: yes
    toc_float: true
    keep_md: true
  github_document:
    toc: yes
fontsize: 11pt
linestretch: 1.2
link-citations: yes
bibliography: bibliography.bib
---


```r
knitr::opts_chunk$set(echo = FALSE)
install.packages("kableExtra")
```

```
## Installing package into '/usr/local/lib/R/site-library'
## (as 'lib' is unspecified)
```

```
## Warning in install.packages("kableExtra"): installation of package 'kableExtra'
## had non-zero exit status
```


```
## Linking to GEOS 3.8.0, GDAL 3.0.4, PROJ 6.3.1
```

```
## Loading required package: sp
```

```
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.0 ──
```

```
## ✓ ggplot2 3.3.3     ✓ purrr   0.3.4
## ✓ tibble  3.1.0     ✓ dplyr   1.0.5
## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
## ✓ readr   1.4.0     ✓ forcats 0.5.1
```

```
## Warning: package 'purrr' was built under R version 4.0.5
```

```
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## x tidyr::extract() masks raster::extract()
## x dplyr::filter()  masks stats::filter()
## x dplyr::lag()     masks stats::lag()
## x dplyr::select()  masks raster::select()
```

```
## 
## Attaching package: 'kableExtra'
```

```
## The following object is masked from 'package:dplyr':
## 
##     group_rows
```


```
## Reading layer `JPN_adm1' from data source `/home/rstudio/class/exercise1/report/JPN_adm1.shp' using driver `ESRI Shapefile'
## Simple feature collection with 47 features and 9 fields
## Geometry type: MULTIPOLYGON
## Dimension:     XY
## Bounding box:  xmin: 122.9332 ymin: 24.04542 xmax: 153.9869 ymax: 45.52279
## Geodetic CRS:  WGS 84
```

```
## 
## ── Column specification ────────────────────────────────────────────────────────
## cols(
##   年次 = col_double(),
##   NL_NAME_1 = col_character(),
##   宿泊計 = col_number(),
##   観光_レクリエーション_宿泊 = col_number(),
##   帰省_知人訪問等_宿泊 = col_number(),
##   出張_業務_宿泊 = col_number(),
##   日帰り計 = col_number(),
##   観光_レクリエーション_日帰り = col_number(),
##   帰省_知人訪問等_日帰り = col_number(),
##   出張_業務_日帰り = col_character()
## )
```

```
## Warning: Missing column names filled in: 'X11' [11], 'X12' [12]
```

```
## 
## ── Column specification ────────────────────────────────────────────────────────
## cols(
##   製造業計 = col_character(),
##   Number = col_double(),
##   NL_NAME_1 = col_character(),
##   年次 = col_double(),
##   事業所数 = col_double(),
##   従業者数 = col_double(),
##   現金給与総額 = col_double(),
##   原材料使用額等 = col_double(),
##   製造品出荷額等 = col_double(),
##   付加価値額 = col_double(),
##   X11 = col_logical(),
##   X12 = col_logical()
## )
```



```
## Joining, by = "NL_NAME_1"
## Joining, by = "NL_NAME_1"
```

```
## Warning: One tm layer group has duplicated layer types, which are omitted. To
## draw multiple layers of the same type, use multiple layer groups (i.e. specify
## tm_shape prior to each of them).
```

![](final_report_files/figure-html/stay_industry-1.png)<!-- -->

```
## [1]   757 11487
```

```
## [1]   448460 44909000
```

![](final_report_files/figure-html/stay_industry-2.png)<!-- -->

```
## [1] 0.3346684
```

```
## 
## 	Pearson's product-moment correlation
## 
## data:  JPN_travel_stay_select$観光_レクリエーション_宿泊 and JPN_industry_select$製造品出荷額等
## t = 2.3824, df = 45, p-value = 0.02149
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.05255211 0.56731318
## sample estimates:
##       cor 
## 0.3346684
```



```
## Warning: One tm layer group has duplicated layer types, which are omitted. To
## draw multiple layers of the same type, use multiple layer groups (i.e. specify
## tm_shape prior to each of them).
```

![](final_report_files/figure-html/day_industry-1.png)<!-- -->

```
## [1]   450 16628
```

```
## [1]   448460 44909000
```

![](final_report_files/figure-html/day_industry-2.png)<!-- -->

```
## [1] 0.5679527
```

```
## 
## 	Pearson's product-moment correlation
## 
## data:  JPN_travel_day_select$観光_レクリエーション_日帰り and JPN_industry_select$製造品出荷額等
## t = 4.629, df = 45, p-value = 3.129e-05
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.3355059 0.7352090
## sample estimates:
##       cor 
## 0.5679527
```
 
 
![](final_report_files/figure-html/stay_day-1.png)<!-- -->

```
## [1] 0.8157327
```

```
## 
## 	Pearson's product-moment correlation
## 
## data:  JPN_travel_stay_select$観光_レクリエーション_宿泊 and JPN_travel_day_select$観光_レクリエーション_日帰り
## t = 9.4603, df = 45, p-value = 2.871e-12
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.6902603 0.8935777
## sample estimates:
##       cor 
## 0.8157327
```


```
## Warning: One tm layer group has duplicated layer types, which are omitted. To
## draw multiple layers of the same type, use multiple layer groups (i.e. specify
## tm_shape prior to each of them).

## Warning: One tm layer group has duplicated layer types, which are omitted. To
## draw multiple layers of the same type, use multiple layer groups (i.e. specify
## tm_shape prior to each of them).

## Warning: One tm layer group has duplicated layer types, which are omitted. To
## draw multiple layers of the same type, use multiple layer groups (i.e. specify
## tm_shape prior to each of them).
```

```
## Legend labels were too wide. The labels have been resized to 0.59, 0.54, 0.54, 0.54, 0.54, 0.52, 0.49. Increase legend.width (argument of tm_layout) to make the legend wider and therefore the labels larger.
```

```
## Warning: One tm layer group has duplicated layer types, which are omitted. To
## draw multiple layers of the same type, use multiple layer groups (i.e. specify
## tm_shape prior to each of them).
```

```
## Legend labels were too wide. The labels have been resized to 0.59, 0.54, 0.54, 0.54, 0.54, 0.52, 0.49. Increase legend.width (argument of tm_layout) to make the legend wider and therefore the labels larger.
```

![](final_report_files/figure-html/arrange_map-1.png)<!-- -->



## 0. 要旨
日本は工業で経済を成長させてきた過去があり、各都道府県で特色のある工業を行っている。また、観光業も盛んになっており各都道府県が様々な施策に取り組んでいる。工業生産額や観光客数などの数字は各都道府県ごとに異なっている。工業の盛んさと観光の盛んさには一定の関係がみいだ工業で経済を成長させてきた過去があり、各都道府県で特色のある工業を行っている。また、観光業も盛んになっており各都道府県が様々な施策に取り組んでいる。工業生産額や観光客数などは自治体にとっても税収などの観点から重要なデータである。何かしらの影響で観光業が打撃を受けても工業が盛んならばそれで補えたり、工業がそこまで盛んでなければ打撃は大きなものとなる。そこで、今回は工業出荷額と観光客数の相関関係について調べた。またその過程で宿泊ありと日帰りの場合の観光客数の差についても調査した。結果は、工業出荷額と観光客数には、宿泊ありと日帰り共に正の相関があると見られた。宿泊ありより日帰りの方が強い相関があった。今回の結果は工業と観光業に関連がある可能性を示唆している。前述の通り、観光業が打撃を受けた際に工業で補えるか、また逆に工業が衰退したときに観光業はどのような影響を受けるか、などを詳細に調べることができれば、より安定した行政運営ができるかもしれない。



## 1. はじめに
### 1.1 背景
日本では工業が経済を担っている大きな柱の1つであると考えられる。また、観光業も同様でインバウンドの経済への影響力は目覚ましいものがある。一方で、近年では自然災害が多発し、土砂災害などで観光地に行くことができず、その地の観光業に大きな影響を与える事例も増えてきている。自治体は観光業で失った税収分などを工業など他で補わなければならない。今回の調査で2つのデータ間に関連性が確認できればあ用な政策に活かせる可能性がある。

### 1.2 目的
今回は工業の中でも工業生産額出荷額に、観光業の中でも観光客数に着目して調査を行った。この2つのデータに相関があるかどうかを調べた。また、視覚的にもそれらの関連性があるかを見いだせるかを調査した。

## 2. 手法
工業生産出荷額と観光客数のデータに関連性があるかどうかの可能性を調べるために、それらのデータ間の相関係数を求めた。また、視覚的にデータを観察するために2つにデータを1つの地図上で表した。また、宿泊ありと日帰りの観光客数のデータの違いについても中央値や平均値を比較することで調べた。

## 3. データ
今回使用したデータは工業生産出荷額が経済産業省が発表した2016年のデータ（https://www.meti.go.jp/statistics/tyo/kougyo/result-2/h29/kakuho/chiiki/index.html） をもとに加工したものである。なお、今回は製造品出荷額等のみに着目した。観光客数のデータはe-Statの2016年のデータ（https://www.e-stat.go.jp/dbview?sid=0003300795） をもとに加工したものである。なお、観光客数のデータは宿泊と日帰りに分かれていたが、今回はそれぞれに着目し、それぞれのデータと製造品出荷額等との関連性を調べた。なお、目的については観光・レクリエーションのみに着目した。

## 4. 結果
最初に宿泊ありと日帰りの観光客数の比較を行う。この2つのデータの相関係数は0.8157327となった。また散布図を図1に示す。散布図からも宿泊ありと日帰りには強い正の相関があることが分かる。また、宿泊ありと日帰りに共通して観光客数が多い県と少ない県の差が大きいことが分かる。

<img src="./final_report_files/figure-html/stay_day-1.png" width="100%" />
$$図1　宿泊ありと日帰りの観光客数の散布図$$

次に宿泊ありの観光客数と製造品出荷額等についてである。相関係数は0.3346684と弱いながらも正の相関が見られた。散布図を図2に示す。日帰りの観光客数と製造品出荷額等の相関係数は0.5679527と正の相関が見られた。


<img src="./final_report_files/figure-html/stay_industry-2.png" width="100%" />

$$図2　宿泊ありの観光客数と製造品出荷額等の散布図$$

最後に日帰りの観光客数と製造品出荷額等についてである。相関係数は0.5679527と正の相関が見られた。また、散布図を図3に示す。


<img src="./final_report_files/figure-html/day_industry-2.png" width="100%" />

$$図3　日帰りの観光客数と製造品出荷額等の散布図$$

また、2つのデータを1つの地図で表した結果は、製造品出荷額等が高く観光客数も多い県と製造品出荷額等が高く観光客数は低い県があり、またその逆もあるため、視覚的に明らかな関連があるとは言えなかった。最後に各データの指標値を表1に示す。


$$表1　各種データの指標値$$


```r
table_data <- matrix(0, 4, 5)

table_data[1,] <- c("","値の範囲","平均値","中央値","製造品出荷額等との相関係数")
table_data[2,] <- c("観光客数（宿泊あり） [千人]","757-11487",3722.106,2970,0.3346684)
table_data[3,] <- c("観光客数（日帰り） [千人]","450-16628", 4388.064,3219,0.5679527)
table_data[4,] <- c("製造品出荷額等 [百万円]","448460-44909000",6429472,4112832,"")

data1 <- table_data %>%
  kbl() %>%
  kable_material(c("striped", "hover"))

data1
```

<table class=" lightable-material lightable-striped lightable-hover" style='font-family: "Source Sans Pro", helvetica, sans-serif; margin-left: auto; margin-right: auto;'>
<tbody>
  <tr>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 値の範囲 </td>
   <td style="text-align:left;"> 平均値 </td>
   <td style="text-align:left;"> 中央値 </td>
   <td style="text-align:left;"> 製造品出荷額等との相関係数 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 観光客数（宿泊あり） [千人] </td>
   <td style="text-align:left;"> 757-11487 </td>
   <td style="text-align:left;"> 3722.106 </td>
   <td style="text-align:left;"> 2970 </td>
   <td style="text-align:left;"> 0.3346684 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 観光客数（日帰り） [千人] </td>
   <td style="text-align:left;"> 450-16628 </td>
   <td style="text-align:left;"> 4388.064 </td>
   <td style="text-align:left;"> 3219 </td>
   <td style="text-align:left;"> 0.5679527 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 製造品出荷額等 [百万円] </td>
   <td style="text-align:left;"> 448460-44909000 </td>
   <td style="text-align:left;"> 6429472 </td>
   <td style="text-align:left;"> 4112832 </td>
   <td style="text-align:left;">  </td>
  </tr>
</tbody>
</table>



## 5. 考察
宿泊ありの観光客と日帰りの観光客、製造品出荷額等のデータはいずれも最大値と最小値に差があることが分かった。また、それぞれのデータの中央値と平均値、散布図から考えると、大きな値を持つデータが少なく、多くは値が小さいことが分かる。これは、相関係数に影響を及ぼしていると考えられる。仮に、値の大きなデータを削除して相関係数を計算すると、値は変わると考えられる。相関係数を計算した結果からは宿泊する観光客数と製造品出荷額等より、日帰りの観光客数の方が強い相関があることがわかる。これは、日帰りで行く旅行は身近な場所でも行けるため、弱い相関が見られたが、これは値が大きなデータが存在するためであると思われる。データの中には工業生産出荷額や観光客数が飛び抜けて大きなものがあり、これが相関係数に大きく影響を及ぼしたと考えられる。このデータが存在しないと考えると相関係数の値は小さくなり、相関が弱くなると考えられる。

## 6. 結論
今回は各都道府県別の工業生産出荷額と観光客数について関連性を調査した。これらのデータ間に弱い相関が見られたが、それはある種の外れ値に影響された結果で実際にはそこまで相関がないと考えられる。今回の調査では工業生産出荷額と観光客数の間に相関がある可能性があることが分かったのみで実際の関連性については明らかにできなかった。

## 7. Graphic Abstract

```r
knitr::include_graphics("./final_report_files/figure-html/arrange_map-1.png")
```

<img src="./final_report_files/figure-html/arrange_map-1.png" width="100%" />


## 8. 参考文献
