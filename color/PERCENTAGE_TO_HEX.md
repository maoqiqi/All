# 透明度百分比和十六进制对应关系以及计算方法

十六进制颜色表示是00\~FF,换成十进制就是1\~255,百分比是1%~100%.
由此可知(255/100%)=(X/Y%),由Y得出X后四舍五入再换算成16进制即可.
比如50%得出的是127.5,四舍五入则为128,对应的十六进制则为8\*16+0\*16=80.


## 目录

* [透明度百分比和十六进制对应关系计算方法](#透明度百分比和十六进制对应关系计算方法)
* [透明度百分比和十六进制对应关系表格](#透明度百分比和十六进制对应关系表格)
* [About](#About)
* [License](#License)


## 透明度百分比和十六进制对应关系计算方法

```
public class PercentageToHex {

    public static void main(String[] args) {
        System.out.println("透明度百分比对应的十六进制:");
        for (int i = 0; i <= 100; i++) {
            // 四舍五入
            int alpha = (int) Math.round(i / 100d * 255);
            String hex = Integer.toHexString(alpha).toUpperCase();
            if (hex.length() == 1) hex = "0" + hex;
            System.out.println(String.format("%d%% — %s", i, hex));
        }
    }
}
```


## 透明度百分比和十六进制对应关系表格

|透明度百分比|十六进制|
|:--------:|:------:|
|     0%   |   00   |
|     1%   |   03   |
|     2%   |   05   |
|     3%   |   08   |
|     4%   |   0A   |
|     5%   |   0D   |
|     6%   |   0F   |
|     7%   |   12   |
|     8%   |   14   |
|     9%   |   17   |
|    10%   |   1A   |
|    11%   |   1C   |
|    12%   |   1F   |
|    13%   |   21   |
|    14%   |   24   |
|    15%   |   26   |
|    16%   |   29   |
|    17%   |   2B   |
|    18%   |   2E   |
|    19%   |   30   |
|    20%   |   33   |
|    21%   |   36   |
|    22%   |   38   |
|    23%   |   3B   |
|    24%   |   3D   |
|    25%   |   40   |
|    26%   |   42   |
|    27%   |   45   |
|    28%   |   47   |
|    29%   |   4A   |
|    30%   |   4D   |
|    31%   |   4F   |
|    32%   |   52   |
|    33%   |   54   |
|    34%   |   57   |
|    35%   |   59   |
|    36%   |   5C   |
|    37%   |   5E   |
|    38%   |   61   |
|    39%   |   63   |
|    40%   |   66   |
|    41%   |   69   |
|    42%   |   6B   |
|    43%   |   6E   |
|    44%   |   70   |
|    45%   |   73   |
|    46%   |   75   |
|    47%   |   78   |
|    48%   |   7A   |
|    49%   |   7D   |
|    50%   |   80   |
|    51%   |   82   |
|    52%   |   85   |
|    53%   |   87   |
|    54%   |   8A   |
|    55%   |   8C   |
|    56%   |   8F   |
|    57%   |   91   |
|    58%   |   94   |
|    59%   |   96   |
|    60%   |   99   |
|    61%   |   9C   |
|    62%   |   9E   |
|    63%   |   A1   |
|    64%   |   A3   |
|    65%   |   A6   |
|    66%   |   A8   |
|    67%   |   AB   |
|    68%   |   AD   |
|    69%   |   B0   |
|    70%   |   B3   |
|    71%   |   B5   |
|    72%   |   B8   |
|    73%   |   BA   |
|    74%   |   BD   |
|    75%   |   BF   |
|    76%   |   C2   |
|    77%   |   C4   |
|    78%   |   C7   |
|    79%   |   C9   |
|    80%   |   CC   |
|    81%   |   CF   |
|    82%   |   D1   |
|    83%   |   D4   |
|    84%   |   D6   |
|    85%   |   D9   |
|    86%   |   DB   |
|    87%   |   DE   |
|    88%   |   E0   |
|    89%   |   E3   |
|    90%   |   E6   |
|    91%   |   E8   |
|    92%   |   EB   |
|    93%   |   ED   |
|    94%   |   F0   |
|    95%   |   F2   |
|    96%   |   F5   |
|    97%   |   F7   |
|    98%   |   FA   |
|    99%   |   FC   |
|   100%   |   FF   |


## About

* **作者**：March
* **邮箱**：fengqi.mao.march@gmail.com
* **头条**：https://toutiao.io/u/425956/subjects
* **简书**：https://www.jianshu.com/u/02f2491c607d
* **掘金**：https://juejin.im/user/5b484473e51d45199940e2ae
* **知乎**：http://zhihu.com/people/maofengqi
* **豆瓣**：https://www.douban.com/people/maofengqi/
* **CSDN**：http://blog.csdn.net/u011810138
* **Github**：https://github.com/maoqiqi
* **开源中国**：https://my.oschina.net/maoqiqi
* **喜马拉雅听书**：https://www.ximalaya.com/zhubo/31419312/
* **SegmentFault**：https://segmentfault.com/u/maoqiqi
* **StackOverFlow**：https://stackoverflow.com/users/8223522


## License

```
   Copyright 2019 maoqiqi

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```