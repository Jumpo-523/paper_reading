# 内生性の問題と操作変数に関して


## 書いてあること

1. Krueger and Dale(1999)を例に内生性の問題を説明する。
2. 内生性ってどうして発生するのか？
    - mis-specification
    <!-- - Dynamic Panel Data Model. -->
    - Simultaneous Equation Biases 
    - measurement Error
    - Selection Bias
    - and more.
3. 回避する一つの方法として操作変数法というものがある。


社会科学でよく「その回帰分析は内生性問題を抱えている」とか耳にします。これは、疫学でいうところの交絡問題(Confounding Problem)と本質的には一緒だと考えており、モデルの外のある変数が、説明変数と被説明変数に同時に影響を与えるような状況を考えています。

Krueger and Dale(1999)での分析を例にあげるとします。
彼らは一流大学での教育を受けることの生涯賃金への影響を分析したいと考えていました。しかし、Y：生涯賃金、Xを教育水準に設定し単純に回帰分析すると、上記の内生生の問題が発生してしまいます。

どういうことか、このケースでは、図の一番したの四角内に交絡要因が描かれています。
先天的能力・野望・辛抱強さなど、時に観察出来ない変数が、一流大学で教育を受ける or notと、生涯賃金両方に影響を与えているということを示している図です。

このような状況下では「一流大学で教育を受ける」学生は元々先天的な能力が高く、生涯賃金が高くなったのは先天的な能力に依るところが大きいだけかもしれません。

つまり、一流大学で教育を受けることの効果が正しく推定出来なくなってしまうのです。（この場合、「一流大学で教育を受けることの効果」は真の値よりも大きく推定されてしまう。（正の方向にバイアスがかかる。））

実際に「正の方向にバイアスがかかる」状況を確認しましょう。（交絡要因を「先天的能力」に絞って話を進めます。）

本来真のモデルが以下のようだと仮定します。  

$y_i = \alpha + \delta t_i + \beta x_i +  \varepsilon_i$

ここで、$y_i$ は生涯賃金、$t_i$ が一流大学で教育を受けたか否かを表す変数で、その係数が $\delta$です。
$x_i$は先天的能力を表す変数で$\beta$がその $y_i$ へのとします。$\varepsilon_i$は正規分布に従う誤差とします。


今、先天的能力を考慮せずに、$\{y_i, t_i\}^N_{i=1}$のデータセットが観察されたとして、下記のような回帰式の元、分析を実行したとします。

$y_i = \alpha + \delta t_i + \epsilon_i$

この分析は単回帰となるので、推定量である $\alpha$, $\delta$ は、

# TBD!!





$Y = X\beta + \epsilon$


$E[\epsilon|X] = 0$が成り立つから、真のパラメータ$\beta$が推定できるのであるが。。  
実際はいくつか推定に必要な変数をモデルに入れていなかったりすることで、推定したいパラメータにバイアスが入ることがある。

例えば、
真のモデルが、
$Y = X_1\beta_1 + X_2\beta_2 + \epsilon$

だったとする。

しかし$X_2$を分析に利用しないことで、

$Y = X_1\beta_1 + \epsilon$



参考文献：

Greene 2010