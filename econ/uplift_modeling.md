CATE(conditional Average Treatment Effect):  
$\tau(X_i) = E[Y_i(1)|X_i] - E[Y_i(0)|X_i]$

もちろん、分析者はiさんに関して両方見ることはできない。（例：心疾患の患者iさんに対してある手術を行った時と行わなかった時、2年後死亡するかしないかの両方を観察することはできない）

だからと言って現状持っている観察データから、下記を因果効果とするのは、残念ながら間違っている。

$E[Y^{obs}_i|X_i=x, W_i = 1] - 
E[Y^{obs}_i|X_i=x, W_i = 0]$

### どう言うことか？

- 上記式は、「**Xがxの人々の**施策Wを受けた人のYの平均と受けなかった人の差分」を示している。これが施策WによるYへの因果効果として解釈するためには、Xに条件付けた上で、WとY(0),Y(1)間で独立であると言う仮定が必要になる。
<!-- 上記の仮定が満たされない -->

例：

    Ojima and Hagiwara(2007)では、日本の小学校における英語教育の日本語学習への悪影響を検証している。彼らの研究によると、「英語教育を行っている学校」と「英語教育を行っていない学校」の生徒間での国語のテストの平均得点の差分が有意に異なっており、「英語教育を行っていない学校」の方が高かった。
    しかし、無作為割り当てで英語教育実施校が決まっていたわけではなく、「英語教育を行っていない学校」の学区は主に転勤族がよく住む地域だったようで、英語教育の実施（treatment）と国語テスト（Outcome）に対して、親の学歴・教育費（X）が影響(交絡)している懸念があった。
    彼らはそれらのXを共変量として調整した上で、もう一度分析を行ったところ、差分はあれど有意ではない、との結果を得ることができた。

上記の例を踏まえると、  
<!-- <font size=3></font> -->
X(親の学歴・教育費) を条件付け**なかったら**、  
W（英語教育）と、  
"Y(W=1)"（英語教育を受けた時の国語のテスト得点）及び  
"Y(W=0)"（英語教育を受けなかった時の国語のテスト得点）
は相関していた!と考えられる。


W（英語教育）が実施されている地域は、そもそも






CATE（Conditional Averaged Treatment Effect）
---

- Uplift modeling boils down to modeling P(Z_i = 1 | X_i).

p^{hat}(x) is consistent estimator of the PS p(X_i).

- Jaskowski and Jaroszewicz(2012)
    - 
- Athey and Imbens(2015)
    - transformed outcome variable.


CIAが付いて回る。


$P(Y=1|X_1,..., X_m, G=\bold{T}) - P(Y=1|X_1,..., X_m, G= \bold{C} )$

- 施策を打った(in the Treatment Group)ことにより、どれだけ「成功」(Y=1)につながったか？
- treatment とcontrol群の成功確率の差をUpliftと呼ぶ。


$\tau(X_i) = 2 P(Z_i=1|X_i) - 1$

-　このセッティングでは、目的変数が二値変数で(分類問題である為)control／treatment群が調整されたケースにしか適応できない。

不均衡な二群に対してかつ、回帰法を利用した手法がAthey and Imbens(2015)nide
開発されている。

<font size=5>

$Y^*_i = Y_i(1)\frac{W_i}{\hat{p}(X_i)} - Y_i(0)\frac{1 - W_i}{1- \hat{p}(X_i)}$

</font>

上記式のように変形すると、CIAの元で、$E[Y^*_i|X_i] = \tau(X_i)$となることが証明されている。
つまり、「$E[Y^*_i|X_i]$の一致推定量はCATEの一致推定量である」ということが言える。



どういう使われ方をされているのか？
>　複数の広告をみた際の効果推定
- https://cyberagent.ai/blog/research/economics/12482/




<!-- ここで証明を確認 -->

- 評価

Z-scoreが同じ人々は同じような行動をするという仮定をする（cf:傾向スコア法の推定時の仮定）

uplift curveの見方。


Reference
----

- Jskwski, Macuej and Szymon Jaroszewicz. uplift modeling for clinical trial data.


<!-- スーパーの需要予測値引き 
時間帯制御しないで、価格（割引き後）と売り上げの関係をみて、「安くすると利益上がる」と推定したとします。
しかし、スーパーの割引きは大体閉店間近で、きている客層が違うことが予想されるため、四時台に価格を下げることが必ずしも利益をあげるとは限らない。
-->