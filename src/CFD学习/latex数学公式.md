# Latex 公式编辑写法速查



![img](latex%E6%95%B0%E5%AD%A6%E5%85%AC%E5%BC%8F/media/logo-16323978846531.png)

[**LaTeX**](https://www.latex-project.org/) 是一种高质量的排版格式，可以生成复杂的表格与数学公式，是当前电子与数学出版行业的事实标准。本文以 [**Pandoc**](https://www.pandoc.org/) 作为 LaTex 渲染引擎（一款用于标记语言文档转换的命令行工具），分门别类的总结了撰写数学公式所需要经常使用到的 LaTeX 语法，方便写作相关科技类文章时随手查阅。



## 保留字符

LaTeX 环境中具有特殊含义的保留字符，不能直接使用，必须通过指定的语法实现：

| 序号  |   符号    |   LaTeX   | 序号  |                   符号                   |                  LaTeX                  |
| :---: | :-------: | :-------: | :---: | :--------------------------------------: | :-------------------------------------: |
| **1** |  $ \# $   |   `\#`    | **6** |                   $\{$                   |                  `\{`                   |
| **2** |   $\%$    |   `\%`    | **7** |                   $\}$                   |                  `\}`                   |
| **3** | $^\wedge$ | `^\wedge` | **8** |                  $\sim$                  |                 `\sim`                  |
| **4** |   $\&$    |   `\&`    | **9** |               $\backslash$               |              `\backslash`               |
| **5** |   $\_$    |   `\_`    |       | ` \\( \int x dx = \frac{x^2}{2} + C \\)` | $\\( \int x dx = \frac{x^2}{2} + C \\)$ |

## 希腊字母

|  序号  |  标准符号  |   LaTeX    | 首字母大写 |   LaTeX    | 使用 `var` 前缀 |     LaTeX     |    读音     |
| :----: | :--------: | :--------: | :--------: | :--------: | :-------------: | :-----------: | :---------: |
| **1**  |  $\alpha$  |  `\alpha`  |            |            |                 |               |   /ˈælfə/   |
| **2**  |  $\beta$   |  `\beta`   |            |            |                 |               |  /ˈbeɪtə/   |
| **3**  |  $\gamma$  |  `\gamma`  |  $\Gamma$  |  `\Gamma`  |   $\varGamma$   |  `\varGamma`  |   /ˈɡæmə/   |
| **4**  |  $\delta$  |  `\delta`  |  $\Delta$  |  `\Delta`  |   $\varDelta$   |  `\varDelta`  |  /ˈdɛltə/   |
| **5**  | $\epsilon$ | `\epsilon` |            |            |  $\varepsilon$  | `\varepsilon` | /ˈɛpsɪlɒn/  |
| **6**  |  $\zeta$   |  `\zeta`   |            |            |                 |               |  /ˈzeɪtə/   |
| **7**  |   $\eta$   |   `\eta`   |            |            |   $\varTheta$   |  `\varTheta`  |   /ˈeɪtə/   |
| **8**  |  $\theta$  |  `\theta`  |  $\Theta$  |  `\Theta`  |   $\vartheta$   |  `\vartheta`  |  /ˈθiːtə/   |
| **9**  |  $\iota$   |  `\iota`   |            |            |                 |               |  /aɪˈoʊtə/  |
| **10** |  $\kappa$  |  `\kappa`  |            |            |   $\varkappa$   |  `\varkappa`  |   /ˈkæpə/   |
| **11** | $\lambda$  | `\lambda`  | $\Lambda$  | `\Lambda`  |  $\varLambda$   | `\varLambda`  |  /ˈlæmdə/   |
| **12** |   $\mu$    |   `\mu`    |            |            |                 |               |   /mjuː/    |
| **13** |   $\nu$    |   `\nu`    |            |            |                 |               |   /njuː/    |
| **14** |   $\xi$    |   `\xi`    |   $\Xi$    |   `\Xi`    |    $\varXi$     |   `\varXi`    | /zaɪ, ksaɪ/ |
| **15** |    $o$     |    `o`     |    $O$     |    `O`     |    $\varPi$     |   `\varPi`    | /ˈɒmɪkrɒn/  |
| **16** |   $\pi$    |   `\pi`    |   $\Pi$    |   `\Pi`    |    $\varpi$     |   `\varpi`    |    /paɪ/    |
| **17** |   $\rho$   |   `\rho`   |            |            |    $\varrho$    |   `\varrho`   |    /roʊ/    |
| **18** |  $\sigma$  |  `\sigma`  |  $\Sigma$  |  `\Sigma`  |   $\varsigma$   |  `\varsigma`  |  /ˈsɪɡmə/   |
| **19** |   $\tau$   |   `\tau`   |            |            |   $\varSigma$   |  `\varSigma`  | /taʊ, tɔː/  |
| **20** | $\upsilon$ | `\upsilon` | $\Upsilon$ | `\Upsilon` |  $\varUpsilon$  | `\varUpsilon` | /ˈʌpsɪlɒn/  |
| **21** |   $\phi$   |   `\phi`   |   $\Phi$   |   `\Phi`   |    $\varphi$    |   `\varphi`   |    /faɪ/    |
| **22** |   $\chi$   |   `\chi`   |            |            |    $\varPhi$    |   `\varPhi`   |    /kaɪ/    |
| **23** |   $\psi$   |   `\psi`   |   $\Psi$   |   `\Psi`   |    $\varPsi$    |   `\varPsi`   |   /psaɪ/    |
| **24** |  $\omega$  |  `\omega`  |  $\Omega$  |  `\Omega`  |   $\varOmega$   |  `\varOmega`  | /oʊˈmeɪɡə/  |
| **25** | $\digamma$ | `\digamma` |            |            |                 |               | /daɪ'gæmə/  |

## 希伯来字母

| 序号  |   符号   |  LaTeX   | 英文  | 序号  |   符号    |   LaTeX   |  英文  |
| :---: | :------: | :------: | :---: | :---: | :-------: | :-------: | :----: |
| **1** | $\aleph$ | `\aleph` | aleph | **3** | $\gimel$  | `\gimel`  | gimel  |
| **2** | $\beth$  | `\beth`  | beth  | **4** | $\daleth$ | `\daleth` | daleth |

## 二元运算符

|  序号  |       符号       |      LaTeX       |  序号  |        符号        |       LaTeX        |
| :----: | :--------------: | :--------------: | :----: | :----------------: | :----------------: |
| **1**  |       $+$        |       `+`        | **20** |     $\bullet$      |     `\bullet`      |
| **2**  |       $-$        |       `-`        | **21** |      $\oplus$      |      `\oplus`      |
| **3**  |     $\times$     |     `\times`     | **22** |     $\ominus$      |     `\ominus`      |
| **4**  |      $\div$      |      `\div`      | **23** |      $\odot$       |      `\odot`       |
| **5**  |      $\pm$       |      `\pm`       | **24** |     $\oslash$      |     `\oslash`      |
| **6**  |      $\mp$       |      `\mp`       | **25** |     $\otimes$      |     `\otimes`      |
| **7**  | $\triangleleft$  | `\triangleleft`  | **26** |     $\bigcirc$     |     `\bigcirc`     |
| **8**  | $\triangleright$ | `\triangleright` | **27** |     $\diamond$     |     `\diamond`     |
| **9**  |     $\cdot$      |     `\cdot`      | **28** |      $\uplus$      |      `\uplus`      |
| **10** |   $\setminus$    |   `\setminus`    | **29** |  $\bigtriangleup$  |  `\bigtriangleup`  |
| **11** |     $\star$      |     `\star`      | **30** | $\bigtriangledown$ | `\bigtriangledown` |
| **12** |      $\ast$      |      `\ast`      | **31** |       $\lhd$       |       `\lhd`       |
| **13** |      $\cup$      |      `\cup`      | **32** |       $\rhd$       |       `\rhd`       |
| **14** |      $\cap$      |      `\cap`      | **33** |      $\unlhd$      |      `\unlhd`      |
| **15** |     $\sqcup$     |     `\sqcup`     | **34** |      $\unrhd$      |      `\unrhd`      |
| **16** |     $\sqcap$     |     `\sqcap`     | **35** |      $\amalg$      |      `\amalg`      |
| **17** |      $\vee$      |      `\vee`      | **36** |       $\wr$        |       `\wr`        |
| **18** |     $\wedge$     |     `\wedge`     | **37** |     $\dagger$      |     `\dagger`      |
| **19** |     $\circ$      |     `\circ`      | **38** |     $\ddagger$     |     `\ddagger`     |

## 二元关系符

|  序号  |                   符号                   |                  LaTeX                   |  序号  |      符号      |     LaTeX      |
| :----: | :--------------------------------------: | :--------------------------------------: | :----: | :------------: | :------------: |
| **1**  |                   $=$                    |                   `=`                    | **49** |    $\gneq$     |    `\gneq`     |
| **2**  |                  $\ne$                   |                  `\ne`                   | **50** |    $\geqq$     |    `\geqq`     |
| **3**  |                  $\neq$                  |                  `\neq`                  | **51** |    $\ngeq$     |    `\ngeq`     |
| **4**  |                 $\equiv$                 |                 `\equiv`                 | **52** |    $\ngeqq$    |    `\ngeqq`    |
| **5**  |               $\not\equiv$               |               `\not\equiv`               | **53** |    $\gneqq$    |    `\gneqq`    |
| **6**  |                 $\doteq$                 |                 `\doteq`                 | **54** |  $\gvertneqq$  |  `\gvertneqq`  |
| **7**  |               $\doteqdot$                |               `\doteqdot`                | **55** |   $\lessgtr$   |   `\lessgtr`   |
| **8**  | $\overset{\underset{\mathrm{def}}{}}{=}$ | `\overset{\underset{\mathrm{def}}{}}{=}` | **56** |  $\lesseqgtr$  |  `\lesseqgtr`  |
| **9**  |                   $:=$                   |                   `:=`                   | **57** | $\lesseqqgtr$  | `\lesseqqgtr`  |
| **10** |                  $\sim$                  |                  `\sim`                  | **58** |   $\gtrless$   |   `\gtrless`   |
| **11** |                 $\nsim$                  |                 `\nsim`                  | **59** |  $\gtreqless$  |  `\gtreqless`  |
| **12** |                $\backsim$                |                `\backsim`                | **60** | $\gtreqqless$  | `\gtreqqless`  |
| **13** |               $\thicksim$                |               `\thicksim`                | **61** |  $\leqslant$   |  `\leqslant`   |
| **14** |                 $\simeq$                 |                 `\simeq`                 | **62** |  $\nleqslant$  |  `\nleqslant`  |
| **15** |               $\backsimeq$               |               `\backsimeq`               | **63** | $\eqslantless$ | `\eqslantless` |
| **16** |                 $\eqsim$                 |                 `\eqsim`                 | **64** |  $\geqslant$   |  `\geqslant`   |
| **17** |                 $\cong$                  |                 `\cong`                  | **65** |  $\ngeqslant$  |  `\ngeqslant`  |
| **18** |                 $\ncong$                 |                 `\ncong`                 | **66** | $\eqslantgtr$  | `\eqslantgtr`  |
| **19** |                $\approx$                 |                `\approx`                 | **67** |   $\lesssim$   |   `\lesssim`   |
| **20** |              $\thickapprox$              |              `\thickapprox`              | **68** |    $\lnsim$    |    `\lnsim`    |
| **21** |               $\approxeq$                |               `\approxeq`                | **69** | $\lessapprox$  | `\lessapprox`  |
| **22** |                 $\asymp$                 |                 `\asymp`                 | **70** |  $\lnapprox$   |  `\lnapprox`   |
| **23** |                $\propto$                 |                `\propto`                 | **71** |   $\gtrsim$    |   `\gtrsim`    |
| **24** |               $\varpropto$               |               `\varpropto`               | **72** |    $\gnsim$    |    `\gnsim`    |
| **25** |                   $<$                    |                   `<`                    | **73** |  $\gtrapprox$  |  `\gtrapprox`  |
| **26** |                 $\nless$                 |                 `\nless`                 | **74** |  $\gnapprox$   |  `\gnapprox`   |
| **27** |                  $\ll$                   |                  `\ll`                   | **75** |    $\prec$     |    `\prec`     |
| **28** |                $\not\ll$                 |                `\not\ll`                 | **76** |    $\nprec$    |    `\nprec`    |
| **29** |                  $\lll$                  |                  `\lll`                  | **77** |   $\preceq$    |   `\preceq`    |
| **30** |                $\not\lll$                |                `\not\lll`                | **78** |   $\npreceq$   |   `\npreceq`   |
| **31** |                $\lessdot$                |                `\lessdot`                | **79** |  $\precneqq$   |  `\precneqq`   |
| **32** |                   $>$                    |                   `>`                    | **80** |    $\succ$     |    `\succ`     |
| **33** |                 $\ngtr$                  |                 `\ngtr`                  | **81** |    $\nsucc$    |    `\nsucc`    |
| **34** |                  $\gg$                   |                  `\gg`                   | **82** |   $\succeq$    |   `\succeq`    |
| **35** |                $\not\gg$                 |                `\not\gg`                 | **83** |   $\nsucceq$   |   `\nsucceq`   |
| **36** |                  $\ggg$                  |                  `\ggg`                  | **84** |  $\succneqq$   |  `\succneqq`   |
| **37** |                $\not\ggg$                |                `\not\ggg`                | **85** | $\preccurlyeq$ | `\preccurlyeq` |
| **38** |                $\gtrdot$                 |                `\gtrdot`                 | **86** | $\curlyeqprec$ | `\curlyeqprec` |
| **39** |                  $\le$                   |                  `\le`                   | **87** | $\succcurlyeq$ | `\succcurlyeq` |
| **40** |                  $\leq$                  |                  `\leq`                  | **88** | $\curlyeqsucc$ | `\curlyeqsucc` |
| **41** |                 $\lneq$                  |                 `\lneq`                  | **89** |   $\precsim$   |   `\precsim`   |
| **42** |                 $\leqq$                  |                 `\leqq`                  | **90** |  $\precnsim$   |  `\precnsim`   |
| **43** |                 $\nleq$                  |                 `\nleq`                  | **91** | $\precapprox$  | `\precapprox`  |
| **44** |                 $\nleqq$                 |                 `\nleqq`                 | **92** | $\precnapprox$ | `\precnapprox` |
| **45** |                 $\lneqq$                 |                 `\lneqq`                 | **93** |   $\succsim$   |   `\succsim`   |
| **46** |               $\lvertneqq$               |               `\lvertneqq`               | **94** |  $\succnsim$   |  `\succnsim`   |
| **47** |                  $\ge$                   |                  `\ge`                   | **95** | $\succapprox$  | `\succapprox`  |
| **48** |                  $\geq$                  |                  `\geq`                  | **96** | $\succnapprox$ | `\succnapprox` |

## 几何符号

|  序号  |        符号         |        LaTeX        |  序号  |         符号          |         LaTeX         |
| :----: | :-----------------: | :-----------------: | :----: | :-------------------: | :-------------------: |
| **1**  |     $\parallel$     |     `\parallel`     | **14** |      $\lozenge$       |      `\lozenge`       |
| **2**  |    $\nparallel$     |    `\nparallel`     | **15** |    $\blacklozenge$    |    `\blacklozenge`    |
| **3**  |  $\shortparallel$   |  `\shortparallel`   | **16** |      $\bigstar$       |      `\bigstar`       |
| **4**  |  $\nshortparallel$  |  `\nshortparallel`  | **17** |      $\bigcirc$       |      `\bigcirc`       |
| **5**  |       $\perp$       |       `\perp`       | **18** |      $\triangle$      |      `\triangle`      |
| **6**  |      $\angle$       |      `\angle`       | **19** |   $\bigtriangleup$    |   `\bigtriangleup`    |
| **7**  |  $\sphericalangle$  |  `\sphericalangle`  | **20** |  $\bigtriangledown$   |  `\bigtriangledown`   |
| **8**  |  $\measuredangle$   |  `\measuredangle`   | **21** |    $\vartriangle$     |    `\vartriangle`     |
| **9**  |     $45^\circ$      |     `45^\circ`      | **22** |    $\triangledown$    |    `\triangledown`    |
| **10** |       $\Box$        |       `\Box`        | **23** |   $\blacktriangle$    |   `\blacktriangle`    |
| **11** |   $\blacksquare$    |   `\blacksquare`    | **24** | $\blacktriangledown$  | `\blacktriangledown`  |
| **12** |     $\diamond$      |     `\diamond`      | **25** | $\blacktriangleleft$  | `\blacktriangleleft`  |
| **13** | $\Diamond \lozenge$ | `\Diamond \lozenge` | **26** | $\blacktriangleright$ | `\blacktriangleright` |

## 逻辑符号

|  序号  |       符号       |      LaTeX       |  序号  |          符号          |         LaTeX          |
| :----: | :--------------: | :--------------: | :----: | :--------------------: | :--------------------: |
| **1**  |    $\forall$     |    `\forall`     | **20** |         $\neg$         |         `\neg`         |
| **2**  |    $\exists$     |    `\exists`     | **21** | $\not\operatorname{R}$ | `\not\operatorname{R}` |
| **3**  |    $\nexists$    |    `\nexists`    | **22** |         $\bot$         |         `\bot`         |
| **4**  |   $\therefore$   |   `\therefore`   | **23** |         $\top$         |         `\top`         |
| **5**  |    $\because$    |    `\because`    | **24** |        $\vdash$        |        `\vdash`        |
| **6**  |      $\And$      |      `\And`      | **25** |        $\dashv$        |        `\dashv`        |
| **7**  |      $\lor$      |      `\lor`      | **26** |        $\vDash$        |        `\vDash`        |
| **8**  |      $\vee$      |      `\vee`      | **27** |        $\Vdash$        |        `\Vdash`        |
| **9**  |   $\curlyvee$    |   `\curlyvee`    | **28** |       $\models$        |       `\models`        |
| **10** |    $\bigvee$     |    `\bigvee`     | **29** |       $\Vvdash$        |       `\Vvdash`        |
| **11** |     $\land$      |     `\land`      | **30** |       $\nvdash$        |       `\nvdash`        |
| **12** |     $\wedge$     |     `\wedge`     | **31** |       $\nVdash$        |       `\nVdash`        |
| **13** |  $\curlywedge$   |  `\curlywedge`   | **32** |       $\nvDash$        |       `\nvDash`        |
| **14** |   $\bigwedge$    |   `\bigwedge`    | **33** |       $\nVDash$        |       `\nVDash`        |
| **15** |    $\bar{q}$     |    `\bar{q}`     | **34** |      $\ulcorner$       |      `\ulcorner`       |
| **16** |   $\bar{abc}$    |   `\bar{abc}`    | **35** |      $\urcorner$       |      `\urcorner`       |
| **17** |  $\overline{q}$  |  `\overline{q}`  | **36** |      $\llcorner$       |      `\llcorner`       |
| **18** | $\overline{abc}$ | `\overline{abc}` | **37** |      $\lrcorner$       |      `\lrcorner`       |
| **19** |     $\lnot$      |     `\lnot`      |        |                        |                        |

## 集合符号

|  序号  |       符号       |      LaTeX       |  序号  |       符号       |      LaTeX       |
| :----: | :--------------: | :--------------: | :----: | :--------------: | :--------------: |
| **1**  |     $\{ \}$      |     `\{ \}`      | **23** |   $\sqsubset$    |   `\sqsubset`    |
| **2**  |   $\emptyset$    |   `\emptyset`    | **24** |    $\supset$     |    `\supset`     |
| **3**  |  $\varnothing$   |  `\varnothing`   | **25** |    $\Supset$     |    `\Supset`     |
| **4**  |      $\in$       |      `\in`       | **26** |   $\sqsupset$    |   `\sqsupset`    |
| **5**  |     $\notin$     |     `\notin`     | **27** |   $\subseteq$    |   `\subseteq`    |
| **6**  |      $\ni$       |      `\ni`       | **28** |   $\nsubseteq$   |   `\nsubseteq`   |
| **7**  |      $\cap$      |      `\cap`      | **29** |   $\subsetneq$   |   `\subsetneq`   |
| **8**  |      $\Cap$      |      `\Cap`      | **30** | $\varsubsetneq$  | `\varsubsetneq`  |
| **9**  |     $\sqcap$     |     `\sqcap`     | **31** |  $\sqsubseteq$   |  `\sqsubseteq`   |
| **10** |    $\bigcap$     |    `\bigcap`     | **32** |   $\supseteq$    |   `\supseteq`    |
| **11** |      $\cup$      |      `\cup`      | **33** |   $\nsupseteq$   |   `\nsupseteq`   |
| **12** |      $\Cup$      |      `\Cup`      | **34** |   $\supsetneq$   |   `\supsetneq`   |
| **13** |     $\sqcup$     |     `\sqcup`     | **35** | $\varsupsetneq$  | `\varsupsetneq`  |
| **14** |    $\bigcup$     |    `\bigcup`     | **36** |  $\sqsupseteq$   |  `\sqsupseteq`   |
| **15** |   $\bigsqcup$    |   `\bigsqcup`    | **37** |   $\subseteqq$   |   `\subseteqq`   |
| **16** |     $\uplus$     |     `\uplus`     | **38** |  $\nsubseteqq$   |  `\nsubseteqq`   |
| **17** |   $\biguplus$    |   `\biguplus`    | **39** |  $\subsetneqq$   |  `\subsetneqq`   |
| **18** |   $\setminus$    |   `\setminus`    | **40** | $\varsubsetneqq$ | `\varsubsetneqq` |
| **19** | $\smallsetminus$ | `\smallsetminus` | **41** |   $\supseteqq$   |   `\supseteqq`   |
| **20** |     $\times$     |     `\times`     | **42** |  $\nsupseteqq$   |  `\nsupseteqq`   |
| **21** |    $\subset$     |    `\subset`     | **43** |  $\supsetneqq$   |  `\supsetneqq`   |
| **22** |    $\Subset$     |    `\Subset`     | **44** | $\varsupsetneqq$ | `\varsupsetneqq` |

## 箭头符号

|  序号  |         符号          |         LaTeX         |  序号  |          符号          |         LaTeX          |
| :----: | :-------------------: | :-------------------: | :----: | :--------------------: | :--------------------: |
| **1**  |    $\Rrightarrow$     |    `\Rrightarrow`     | **36** |     $\longmapsto$      |     `\longmapsto`      |
| **2**  |     $\Lleftarrow$     |     `\Lleftarrow`     | **37** |   $\rightharpoonup$    |   `\rightharpoonup`    |
| **3**  |     $\Rightarrow$     |     `\Rightarrow`     | **38** |  $\rightharpoondown$   |  `\rightharpoondown`   |
| **4**  |    $\nRightarrow$     |    `\nRightarrow`     | **39** |    $\leftharpoonup$    |    `\leftharpoonup`    |
| **5**  |   $\Longrightarrow$   |   `\Longrightarrow`   | **40** |   $\leftharpoondown$   |   `\leftharpoondown`   |
| **6**  |      $\implies$       |      `\implies`       | **41** |    $\upharpoonleft$    |    `\upharpoonleft`    |
| **7**  |     $\Leftarrow$      |     `\Leftarrow`      | **42** |   $\upharpoonright$    |   `\upharpoonright`    |
| **8**  |     $\nLeftarrow$     |     `\nLeftarrow`     | **43** |   $\downharpoonleft$   |   `\downharpoonleft`   |
| **9**  |   $\Longleftarrow$    |   `\Longleftarrow`    | **44** |  $\downharpoonright$   |  `\downharpoonright`   |
| **10** |   $\Leftrightarrow$   |   `\Leftrightarrow`   | **45** |  $\rightleftharpoons$  |  `\rightleftharpoons`  |
| **11** |  $\nLeftrightarrow$   |  `\nLeftrightarrow`   | **46** |  $\leftrightharpoons$  |  `\leftrightharpoons`  |
| **12** | $\Longleftrightarrow$ | `\Longleftrightarrow` | **47** |   $\curvearrowleft$    |   `\curvearrowleft`    |
| **13** |        $\iff$         |        `\iff`         | **48** |   $\circlearrowleft$   |   `\circlearrowleft`   |
| **14** |      $\Uparrow$       |      `\Uparrow`       | **49** |         $\Lsh$         |         `\Lsh`         |
| **15** |     $\Downarrow$      |     `\Downarrow`      | **50** |     $\upuparrows$      |     `\upuparrows`      |
| **16** |    $\Updownarrow$     |    `\Updownarrow`     | **51** |  $\rightrightarrows$   |  `\rightrightarrows`   |
| **17** |     $\rightarrow$     |     `\rightarrow`     | **52** |   $\rightleftarrows$   |   `\rightleftarrows`   |
| **18** |         $\to$         |         `\to`         | **53** |   $\rightarrowtail$    |   `\rightarrowtail`    |
| **19** |    $\nrightarrow$     |    `\nrightarrow`     | **54** |   $\looparrowright$    |   `\looparrowright`    |
| **20** |   $\longrightarrow$   |   `\longrightarrow`   | **55** |   $\curvearrowright$   |   `\curvearrowright`   |
| **21** |     $\leftarrow$      |     `\leftarrow`      | **56** |  $\circlearrowright$   |  `\circlearrowright`   |
| **22** |        $\gets$        |        `\gets`        | **57** |         $\Rsh$         |         `\Rsh`         |
| **23** |     $\nleftarrow$     |     `\nleftarrow`     | **58** |   $\downdownarrows$    |   `\downdownarrows`    |
| **24** |   $\longleftarrow$    |   `\longleftarrow`    | **59** |   $\leftleftarrows$    |   `\leftleftarrows`    |
| **25** |   $\leftrightarrow$   |   `\leftrightarrow`   | **60** |   $\leftrightarrows$   |   `\leftrightarrows`   |
| **26** |  $\nleftrightarrow$   |  `\nleftrightarrow`   | **61** |    $\leftarrowtail$    |    `\leftarrowtail`    |
| **27** | $\longleftrightarrow$ | `\longleftrightarrow` | **62** |    $\looparrowleft$    |    `\looparrowleft`    |
| **28** |      $\uparrow$       |      `\uparrow`       | **63** |   $\hookrightarrow$    |   `\hookrightarrow`    |
| **29** |     $\downarrow$      |     `\downarrow`      | **64** |    $\hookleftarrow$    |    `\hookleftarrow`    |
| **30** |    $\updownarrow$     |    `\updownarrow`     | **65** |      $\multimap$       |      `\multimap`       |
| **31** |      $\nearrow$       |      `\nearrow`       | **66** | $\leftrightsquigarrow$ | `\leftrightsquigarrow` |
| **32** |      $\swarrow$       |      `\swarrow`       | **67** |   $\rightsquigarrow$   |   `\rightsquigarrow`   |
| **33** |      $\nwarrow$       |      `\nwarrow`       | **68** |  $\twoheadrightarrow$  |  `\twoheadrightarrow`  |
| **34** |      $\searrow$       |      `\searrow`       | **69** |  $\twoheadleftarrow$   |  `\twoheadleftarrow`   |
| **35** |       $\mapsto$       |       `\mapsto`       |        |                        |                        |

## 特殊符号

|  序号  |       符号       |      LaTeX       |  序号  |        符号         |        LaTeX        |
| :----: | :--------------: | :--------------: | :----: | :-----------------: | :-----------------: |
| **1**  |     $\infty$     |     `\infty`     | **33** |       $\flat$       |       `\flat`       |
| **2**  |     $\aleph$     |     `\aleph`     | **34** |     $\natural$      |     `\natural`      |
| **3**  |  $\complement$   |  `\complement`   | **35** |      $\sharp$       |      `\sharp`       |
| **4**  |  $\backepsilon$  |  `\backepsilon`  | **36** |      $\diagup$      |      `\diagup`      |
| **5**  |      $\eth$      |      `\eth`      | **37** |     $\diagdown$     |     `\diagdown`     |
| **6**  |     $\Finv$      |     `\Finv`      | **38** |    $\centerdot$     |    `\centerdot`     |
| **7**  |     $\hbar$      |     `\hbar`      | **39** |      $\ltimes$      |      `\ltimes`      |
| **8**  |      $\Im$       |      `\Im`       | **40** |      $\rtimes$      |      `\rtimes`      |
| **9**  |     $\imath$     |     `\imath`     | **41** |  $\leftthreetimes$  |  `\leftthreetimes`  |
| **10** |     $\jmath$     |     `\jmath`     | **42** | $\rightthreetimes$  | `\rightthreetimes`  |
| **11** |     $\Bbbk$      |     `\Bbbk`      | **43** |      $\eqcirc$      |      `\eqcirc`      |
| **12** |      $\ell$      |      `\ell`      | **44** |      $\circeq$      |      `\circeq`      |
| **13** |      $\mho$      |      `\mho`      | **45** |    $\triangleq$     |    `\triangleq`     |
| **14** |      $\wp$       |      `\wp`       | **46** |      $\bumpeq$      |      `\bumpeq`      |
| **15** |      $\Re$       |      `\Re`       | **47** |      $\Bumpeq$      |      `\Bumpeq`      |
| **16** |   $\circledS$    |   `\circledS`    | **48** |     $\doteqdot$     |     `\doteqdot`     |
| **17** |     $\amalg$     |     `\amalg`     | **49** |   $\risingdotseq$   |   `\risingdotseq`   |
| **18** |       $\%$       |       `\%`       | **50** |  $\fallingdotseq$   |  `\fallingdotseq`   |
| **19** |    $\dagger$     |    `\dagger`     | **51** |     $\intercal$     |     `\intercal`     |
| **20** |    $\ddagger$    |    `\ddagger`    | **52** |     $\barwedge$     |     `\barwedge`     |
| **21** |     $\ldots$     |     `\ldots`     | **53** |      $\veebar$      |      `\veebar`      |
| **22** |     $\cdots$     |     `\cdots`     | **54** |  $\doublebarwedge$  |  `\doublebarwedge`  |
| **23** |     $\smile$     |     `\smile`     | **55** |     $\between$      |     `\between`      |
| **24** |     $\frown$     |     `\frown`     | **56** |    $\pitchfork$     |    `\pitchfork`     |
| **25** |      $\wr$       |      `\wr`       | **57** | $\vartriangleleft$  | `\vartriangleleft`  |
| **26** | $\triangleleft$  | `\triangleleft`  | **58** |  $\ntriangleleft$   |  `\ntriangleleft`   |
| **27** | $\triangleright$ | `\triangleright` | **59** | $\vartriangleright$ | `\vartriangleright` |
| **28** |  $\diamondsuit$  |  `\diamondsuit`  | **60** |  $\ntriangleright$  |  `\ntriangleright`  |
| **29** |   $\heartsuit$   |   `\heartsuit`   | **61** |  $\trianglelefteq$  |  `\trianglelefteq`  |
| **30** |   $\clubsuit$    |   `\clubsuit`    | **62** | $\ntrianglelefteq$  | `\ntrianglelefteq`  |
| **31** |   $\spadesuit$   |   `\spadesuit`   | **63** | $\trianglerighteq$  | `\trianglerighteq`  |
| **32** |     $\Game$      |     `\Game`      | **64** | $\ntrianglerighteq$ | `\ntrianglerighteq` |

## 分数

| 类型                    | 符号                                                         | LaTeX                                                        |
| :---------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| **分数**                | $\frac{2}{4}x=0.5x or {2 \over 4}x=0.5x$                     | `\frac{2}{4}x=0.5x or {2 \over 4}x=0.5x`                     |
| **小型分数**            | $\tfrac{2}{4}x = 0.5x$                                       | `\tfrac{2}{4}x = 0.5x`                                       |
| **大型分数** （不嵌套） | $\dfrac{2}{4} = 0.5 \qquad \dfrac{2}{c + \dfrac{2}{d + \dfrac{2}{4}}} = a$ | `\dfrac{2}{4} = 0.5 \qquad \dfrac{2}{c + \dfrac{2}{d + \dfrac{2}{4}}} = a` |
| **大型分数** （嵌套）   | $\cfrac{2}{c + \cfrac{2}{d + \cfrac{2}{4}}} = a$             | `\cfrac{2}{c + \cfrac{2}{d + \cfrac{2}{4}}} = a`             |

## 数值函数

| 符号                                                         | LaTeX                                                        |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| $\exp_a b = a^b, \exp b = e^b, 10^m$                         | `\exp_a b = a^b, \exp b = e^b, 10^m`                         |
| $\ln c, \lg d = \log e, \log_{10} f$                         | `\ln c, \lg d = \log e, \log_{10} f`                         |
| $\sin a, \cos b, \tan c, \cot d, \sec e, \csc f$             | `\sin a, \cos b, \tan c, \cot d, \sec e, \csc f`             |
| $\arcsin a, \arccos b, \arctan c$                            | `\arcsin a, \arccos b, \arctan c`                            |
| $\operatorname{arccot} d, \operatorname{arcsec} e, \operatorname{arccsc} f$ | `\operatorname{arccot} d, \operatorname{arcsec} e, \operatorname{arccsc} f` |
| $\sinh a, \cosh b, \tanh c, \coth d$                         | `\sinh a, \cosh b, \tanh c, \coth d`                         |
| $\operatorname{sh}k, \operatorname{ch}l, \operatorname{th}m, \operatorname{coth}n$ | `\operatorname{sh}k, \operatorname{ch}l, \operatorname{th}m, \operatorname{coth}n` |
| $\operatorname{argsh}o, \operatorname{argch}p, \operatorname{argth}q$ | `\operatorname{argsh}o, \operatorname{argch}p, \operatorname{argth}q` |
| $\operatorname{sgn}r$                                        | `\operatorname{sgn}r`                                        |
| $\left\vert s \right\vert$                                   | `\left\vert s \right\vert`                                   |
| $\min(x,y), \max(x,y)$                                       | `\min(x,y), \max(x,y)`                                       |

如果需要使用特殊的函数符号，那么可以采用 `\operatorname{}` 命令进行自定义：

| 符号                       | LaTeX                      |
| :------------------------- | :------------------------- |
| $\operatorname{mydefine}x$ | `\operatorname{mydefine}x` |

## 根式

| 符号           | LaTeX        | 符号                             | LaTeX                           |
| :------------- | :----------- | :------------------------------- | :------------------------------ |
| $ \surd $      | `\surd`      | $ \sqrt[n]{\pi} $                | `\sqrt[n]{\pi}`                 |
| $ \sqrt{\pi} $ | `\sqrt{\pi}` | $ \sqrt[3]{\frac{x^3+y^3}{2}}* $ | `\sqrt[3]{\frac{x^3+y^3}{2}}*`_ |

## 微分与导数

| 符号                                                         | LaTeX                                                        |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| $dt, \mathrm{d}t, \partial t, \nabla\psi$                    | `dt, \mathrm{d}t, \partial t, \nabla\psi`                    |
| $dy/dx, \mathrm{d}y/\mathrm{d}x, \frac{dy}{dx}, \frac{\mathrm{d}y}{\mathrm{d}x}, \frac{\partial^2}{\partial x_1\partial x_2}y$ | `dy/dx, \mathrm{d}y/\mathrm{d}x, \frac{dy}{dx}, \frac{\mathrm{d}y}{\mathrm{d}x}, \frac{\partial^2}{\partial x_1\partial x_2}y` |
| $\prime, \backprime, f^\prime, f', f'', f^{(3)}, \dot y, \ddot y$ | `\prime, \backprime, f^\prime, f', f'', f^{(3)}, \dot y, \ddot y` |

## 模运算

| 符号                                   | LaTeX                                  |
| :------------------------------------- | :------------------------------------- |
| $s_k \equiv 0 \pmod{m}$                | `s_k \equiv 0 \pmod{m}`                |
| $a \bmod b$                            | `a \bmod b`                            |
| $\gcd(m, n), \operatorname{lcm}(m, n)$ | `\gcd(m, n), \operatorname{lcm}(m, n)` |
| $\mid, \nmid, \shortmid, \nshortmid$   | `\mid, \nmid, \shortmid, \nshortmid`   |

## 极限

| 符号                                | LaTeX                               |
| :---------------------------------- | :---------------------------------- |
| $\lim_{n \to \infty}x_n$            | `\lim_{n \to \infty}x_n`            |
| $\textstyle \lim_{n \to \infty}x_n$ | `\textstyle \lim_{n \to \infty}x_n` |

## 范围与预测

| 符号                                     | LaTeX                                    |
| :--------------------------------------- | :--------------------------------------- |
| $\min x, \max y, \inf s, \sup t$         | `\min x, \max y, \inf s, \sup t`         |
| $\lim u, \liminf v, \limsup w$           | `\lim u, \liminf v, \limsup w`           |
| $\dim p, \deg q, \det m, \ker\phi$       | `\dim p, \deg q, \det m, \ker\phi`       |
| $\Pr j, \hom l, \lVert z \rVert, \arg z$ | `\Pr j, \hom l, \lVert z \rVert, \arg z` |

## 积分

| 符号                                        | LaTeX                                       |
| :------------------------------------------ | :------------------------------------------ |
| $\int\limits_{1}^{3}\frac{e^3/x}{x^2}\, dx$ | `\int\limits_{1}^{3}\frac{e^3/x}{x^2}\, dx` |
| $\int_{1}^{3}\frac{e^3/x}{x^2}\, dx$        | `\int_{1}^{3}\frac{e^3/x}{x^2}\, dx`        |
| $\textstyle \int\limits_{-N}^{N} e^x dx$    | `\textstyle \int\limits_{-N}^{N} e^x dx`    |
| $\textstyle \int_{-N}^{N} e^x dx$           | `\textstyle \int_{-N}^{N} e^x dx`           |
| $\iint\limits_D dx\,dy$                     | `\iint\limits_D dx\,dy`                     |
| $\iiint\limits_E dx\,dy\,dz$                | `\iiint\limits_E dx\,dy\,dz`                |
| $\iiiint\limits_F dx\,dy\,dz\,dt$           | `\iiiint\limits_F dx\,dy\,dz\,dt`           |
| $\int_{(x,y)\in C} x^3\, dx + 4y^2\, dy$    | `\int_{(x,y)\in C} x^3\, dx + 4y^2\, dy`    |
| $\oint_{(x,y)\in C} x^3\, dx + 4y^2\, dy$   | `\oint_{(x,y)\in C} x^3\, dx + 4y^2\, dy`   |

> **注意**：积分符号采用 `\int\_{}^{}` 命令调用，双重积分符号采用 `\iint\_{}^{}`，以此类推，最高可以支持四重积分。

曲线积分可以使用 `\oint` 命令调用，但是 MathJax 并不支持该语法，因此在开启了 Unicode 扩展的前提下，可以改为采用 `\unicode{}` 命令调用：

| 符号                                                         | LaTeX                                                        | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| $\unicode{8751} \unicode{x222F}_C$                           | `\unicode{8751} \unicode{x222F}_C`                           | 曲面积分符号的 Unicode 码十进制为 `8751`,十六进制为 `x222F`； |
| $\unicode{8752} \unicode{x2230}_C$                           | `\unicode{8752} \unicode{x2230}_C`                           | 三维曲面积分符号的 Unicode 码十进制为 `8752`,十六进制为 `x2230`； |
| $\unicode{8753} \unicode{x2231}_c \unicode{8754} \unicode{x2232}_c \unicode{8755} \unicode{x2233}_c$ | `\unicode{8753} \unicode{x2231}_c \unicode{8754} \unicode{x2232}_c \unicode{8755} \unicode{x2233}_c` | 其它积分符号；                                               |

## 大型运算符

| 分类       |        符号         | LaTeX               |              符号              | LaTeX                          |
| :--------- | :-----------------: | :------------------ | :----------------------------: | :----------------------------- |
| **求和**   |   $\sum_{a}^{b}$    | `\sum_{a}^{b}`      |   $\textstyle \sum_{a}^{b}$    | `\textstyle \sum_{a}^{b}`      |
| **连乘积** |   $\prod_{a}^{b}$   | `\prod_{a}^{b}`     |   $\textstyle \prod_{a}^{b}$   | `\textstyle \prod_{a}^{b}`     |
| **余积**   |  $\coprod_{a}^{b}$  | `\coprod_{a}^{b}`   |  $\textstyle \coprod_{a}^{b}$  | `\textstyle \coprod_{a}^{b}`   |
| **并集**   |  $\bigcup_{a}^{b}$  | `\bigcup_{a}^{b}`   |  $\textstyle \bigcup_{a}^{b}$  | `\textstyle \bigcup_{a}^{b}`   |
| **交集**   |  $\bigcap_{a}^{b}$  | `\bigcap_{a}^{b}`   |  $\textstyle \bigcap_{a}^{b}$  | `\textstyle \bigcap_{a}^{b}`   |
| **析取**   |  $\bigvee_{a}^{b}$  | `\bigvee_{a}^{b}`   |  $\textstyle \bigvee_{a}^{b}$  | `\textstyle \bigvee_{a}^{b}`   |
| **合取**   | $\bigwedge_{a}^{b}$ | `\bigwedge_{a}^{b}` | $\textstyle \bigwedge_{a}^{b}$ | `\textstyle \bigwedge_{a}^{b}` |

## 上下标

|           类型           |                             符号                             | 代码                                                         |
| :----------------------: | :----------------------------------------------------------: | :----------------------------------------------------------- |
|         **上标**         |                        $a^2 a^{x+3}$                         | `a^2` `a^{x+3}`                                              |
|         **下标**         |                            $a_2$                             | `a_2`                                                        |
|         **组合**         |                $10^{30} a^{2+2}a{i,j} b{f'}$                 | `10^{30} a^{2+2}` `a{i,j} b{f'}`                             |
|      **上下标混合**      |                        $x_2^3{x_2}^3$                        | `x_2^3` `{x_2}^3`                                            |
|      **上标的上标**      |                        $10^{10^{8}}$                         | `10^{10^{8}}`                                                |
|       **混合标识**       |          $\sideset{1^2}{3^4}X_a^b{}_1^2!\Omega_3^4$          | `\sideset{1^2}{3^4}X_a^b` `{}_1^2!\Omega_3^4`                |
|       **顶标底标**       | $\overset{\alpha}{\omega},\underset{\alpha}{\omega},\overset{\alpha}{\underset{\gamma}{\omega}},\stackrel{\alpha}{\omega}$ | `\overset{\alpha}{\omega}` `\underset{\alpha}{\omega}` `\overset{\alpha}{\underset{\gamma}{\omega}}` `\stackrel{\alpha}{\omega}` |
|         **导数**         |        $x', y'', f', f'',x^\prime, y^{\prime\prime}$         | `x', y'', f', f''` `x^\prime, y^{\prime\prime}`              |
|        **导数点**        |                     $\dot{x}, \ddot{x}$                      | `\dot{x}, \ddot{x}`                                          |
|    **上下划线与向量**    | $\hat a \ \bar b \ \vec c,\overrightarrow{a b} \ \overleftarrow{c d} \ \widehat{d e f},\overline{g h i} \ \underline{j k l}$ | `\hat a \ \bar b \ \vec c` `\overrightarrow{a b} \ \overleftarrow{c d} \ \widehat{d e f}` `\overline{g h i} \ \underline{j k l}` |
|         **弧度**         |                   $\overset{\frown} {AB}$                    | `\overset{\frown} {AB}`                                      |
|         **箭头**         |    $A \xleftarrow{n+\mu-1} B \xrightarrow[T]{n\pm i-1} C$    | `A \xleftarrow{n+\mu-1} B \xrightarrow[T]{n\pm i-1} C`       |
|        **大括号**        |            $\overbrace{ 1+2+\cdots+100 }^{5050}$             | `\overbrace{ 1+2+\cdots+100 }^{5050}`                        |
|      **底部大括号**      |              $\underbrace{ a+b+\cdots+z }_{26}$              | `\underbrace{ a+b+\cdots+z }_{26}`                           |
|       **求和运算**       |                      $\sum_{k=1}^N k^2$                      | `\sum_{k=1}^N k^2`                                           |
| **文本模式下的求和运算** |                $\textstyle \sum_{k=1}^N k^2$                 | `\textstyle \sum_{k=1}^N k^2`                                |
|   **分式中的求和运算**   |                 $\frac{\sum_{k=1}^N k^2}{a}$                 | `\frac{\sum_{k=1}^N k^2}{a}`                                 |
|   **分式中的求和运算**   |          $\frac{\displaystyle \sum_{k=1}^N k^2}{a}$          | `\frac{\displaystyle \sum_{k=1}^N k^2}{a}`                   |
|   **分式中的求和运算**   |            $\frac{\sum\limits^{^N}_{k=1} k^2}{a}$            | `\frac{\sum\limits^{^N}_{k=1} k^2}{a}`                       |
|       **乘积运算**       |                     $\prod_{i=1}^N x_i$                      | `\prod_{i=1}^N x_i`                                          |
|       **乘积运算**       |                $\textstyle \prod_{i=1}^N x_i$                | `\textstyle \prod_{i=1}^N x_i`                               |
|       **副乘运算**       |                    $\coprod_{i=1}^N x_i$                     | `\coprod_{i=1}^N x_i`                                        |
|       **副乘运算**       |               $\textstyle \coprod_{i=1}^N x_i$               | `\textstyle \coprod_{i=1}^N x_i`                             |
|         **极限**         |                   $\lim_{n \to \infty}x_n$                   | `\lim_{n \to \infty}x_n`                                     |
|         **极限**         |             $\textstyle \lim_{n \to \infty}x_n$              | `\textstyle \lim_{n \to \infty}x_n`                          |
|         **积分**         |         $\int\limits_{1}^{3}\frac{e^3/x}{x^2}\, dx$          | `\int\limits_{1}^{3}\frac{e^3/x}{x^2}\, dx`                  |
|         **积分**         |             $\int_{1}^{3}\frac{e^3/x}{x^2}\, dx$             | `\int_{1}^{3}\frac{e^3/x}{x^2}\, dx`                         |
|         **积分**         |           $\textstyle \int\limits_{-N}^{N} e^x dx$           | `\textstyle \int\limits_{-N}^{N} e^x dx`                     |
|         **积分**         |              $\textstyle \int_{-N}^{N} e^x dx$               | `\textstyle \int_{-N}^{N} e^x dx`                            |
|       **双重积分**       |                   $\iint\limits_D dx\,dy$                    | `\iint\limits_D dx\,dy`                                      |
|       **三重积分**       |                 $\iiint\limits_E dx\,dy\,dz$                 | `\iiint\limits_E dx\,dy\,dz`                                 |
|       **四重积分**       |              $\iiiint\limits_F dx\,dy\,dz\,dt$               | `\iiiint\limits_F dx\,dy\,dz\,dt`                            |
|       **路径积分**       |           $\int_{(x,y)\in C} x^3\, dx + 4y^2\, dy$           | `\int_{(x,y)\in C} x^3\, dx + 4y^2\, dy`                     |
|       **环路积分**       |          $\oint_{(x,y)\in C} x^3\, dx + 4y^2\, dy$           | `\oint_{(x,y)\in C} x^3\, dx + 4y^2\, dy`                    |
|         **交集**         |                    $\bigcap_{i=1}^n E_i$                     | `\bigcap_{i=1}^n E_i`                                        |
|         **并集**         |                    $\bigcup_{i=1}^n E_i$                     | `\bigcup_{i=1}^n E_i`                                        |

## 二项式系数

| 类型           | 符号            | LaTeX           |
| :------------- | :-------------- | :-------------- |
| 二项式系数     | $\binom{n}{k}$  | `\binom{n}{k}`  |
| 小型二项式系数 | $\tbinom{n}{k}$ | `\tbinom{n}{k}` |
| 大型二项式系数 | $\dbinom{n}{k}$ | `\dbinom{n}{k}` |

## 矩阵

|                             符号                             |                            LaTeX                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|          $\begin{matrix}x & y \\z & v\end{matrix}$           |          `\begin{matrix}x & y \\z & v\end{matrix}`           |
|                            $yzv$                             |                            xyzv\|                            |
|         $\begin{Vmatrix}x & y \\z & v\end{Vmatrix}$          |         `\begin{Vmatrix}x & y \\z & v\end{Vmatrix}`          |
| $\begin{bmatrix}0 & \cdots & 0 \\\vdots & \ddots & \vdots \\0 & \cdots & 0\end{bmatrix}$ | `\begin{bmatrix}0 & \cdots & 0 \\\vdots & \ddots & \vdots \\0 & \cdots & 0\end{bmatrix}` |
|         $\begin{Bmatrix}x & y \\z & v\end{Bmatrix}$          |         `\begin{Bmatrix}x & y \\z & v\end{Bmatrix}`          |
|         $\begin{pmatrix}x & y \\z & v\end{pmatrix}$          |         `\begin{pmatrix}x & y \\z & v\end{pmatrix}`          |
| $\bigl( \begin{smallmatrix}a&b\\c&d\end{smallmatrix} \bigr)$ | `\bigl( \begin{smallmatrix}a&b\\c&d\end{smallmatrix} \bigr)` |

## 数组

|                             符号                             |      LaTeX      |
| :----------------------------------------------------------: | :-------------: |
| $\begin{array}{ |c |c |c |}a & b & S \\\hline0 & 0 & 1 \\0 & 1 & 1 \\1 & 0 & 1 \\1 & 1 & 0\end{array}$ | $\begin{array}{ |



## 方程与方程组

|                             符号                             |                            LaTeX                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| $\begin{cases}3x + 5y + z \\7x - 2y + 4z \\-6x + 3y + 2z\end{cases}$ | `\begin{cases}3x + 5y + z \\7x - 2y + 4z \\-6x + 3y + 2z\end{cases}` |

### 条件定义

|                             符号                             |                            LaTeX                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| $f(n) =\begin{cases}n/2, & \text{if }n\text{ is even} \\3n+1, & \text{if }n\text{ is odd}\end{cases}$ | `f(n) =\begin{cases}n/2, & \text{if }n\text{ is even} \\3n+1, & \text{if }n\text{ is odd}\end{cases}` |

### 多行等式

|                             符号                             |                            LaTeX                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| $\begin{align}f(x) & = (a+b)^2\\& = a^2+2ab+b^2\end{align}$  | `\begin{align}f(x) & = (a+b)^2\\& = a^2+2ab+b^2\end{align}`  |
| $\begin{alignat}{2}f(x) & = (a-b)^2 \\& = a^2-2ab+b^2\end{alignat}$ | `\begin{alignat}{2}f(x) & = (a-b)^2 \\& = a^2-2ab+b^2\end{alignat}` |
| $\begin{array}{lcl}z & = & a \\f(x,y,z) & = & x + y + z\end{array}$ | `\begin{array}{lcl}z & = & a \\f(x,y,z) & = & x + y + z\end{array}` |
| $\begin{array}{lcr}z & = & a \\f(x,y,z) & = & x + y + z\end{array}$ | `\begin{array}{lcr}z & = & a \\f(x,y,z) & = & x + y + z\end{array}` |

### 自动编号

|                             描述                             |                             符号                             |                            LaTeX                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| 开启 AMS 扩展包的情况下，会在部分环境的多行公式后自动编号；  |   $\begin{eqnarray}E = mc^2 \\e^{i\pi}+1=0\end{eqnarray}$    |   `\begin{eqnarray}E = mc^2 \\e^{i\pi}+1=0\end{eqnarray}`    |
| 整个公式都不进行编号，可以使用`{equation*}`、`{eqnarray*}`环境； |  $\begin{eqnarray*}E = mc^2 \\e^{i\pi}+1=0\end{eqnarray*}$   |  `\begin{eqnarray*}E = mc^2 \\e^{i\pi}+1=0\end{eqnarray*}`   |
| 单个方程不进行编号，可以在指定方程后面添加`\nonumber`命令；  | $\begin{eqnarray}E = mc^2 \\e^{i\pi}+1=0 \nonumber\end{eqnarray}$ | `\begin{eqnarray}E = mc^2 \\e^{i\pi}+1=0 \nonumber\end{eqnarray}` |
| 个别公式出现或者不出现编号，可以在公式后使用`\tag{}`或者`\notag`命令； | $\begin{eqnarray}E = mc^2 \notag\\e^{i\pi}+1=0 \tag{b}\end{eqnarray}$ | `\begin{eqnarray}E = mc^2 \notag\\e^{i\pi}+1=0 \tag{b}\end{eqnarray}` |

## 括号

常用的`()`、`[]`、`{}`括号符号可以在 LaTeX 环境当中直接进行使用，但是如果处于较大的符号当中，就应该配合`\left`和`\right`命令来使用：

| 类型                                      |                             符号                             | LaTeX                                                        |
| :---------------------------------------- | :----------------------------------------------------------: | :----------------------------------------------------------- |
| 圆括号、小括号                            |                $\left ( \frac{a}{b} \right )$                | `\left ( \frac{a}{b} \right )`                               |
| 方括号、中括号                            | $\left [ \frac{a}{b} \right ], \left \lbrack \frac{a}{b} \right \rbrack$ | `\left [ \frac{a}{b} \right ]`, `\left \lbrack \frac{a}{b} \right \rbrack` |
| 花括号、大括号                            | $\left \{ \frac{a}{b} \right \}, \left \lbrace \frac{a}{b} \right \rbrace$ | `\left \{ \frac{a}{b} \right \}`, `\left \lbrace \frac{a}{b} \right \rbrace` |
| 角括号                                    |          $\left \langle \frac{a}{b} \right \rangle$          | `\left \langle \frac{a}{b} \right \rangle`                   |
| 单竖线和双竖线                            |                           $ ‖cd‖$                            | ab\| ‖cd‖                                                    |
| 取整函数与取顶函数                        | $\left \lfloor \frac{a}{b} \right \rfloor,\left \lceil \frac{c}{d} \right \rceil$ | `\left \lfloor \frac{a}{b} \right \rfloor` ,`\left \lceil \frac{c}{d} \right \rceil` |
| 斜线与反斜线                              |           $\left / \frac{a}{b} \right \backslash$            | `\left / \frac{a}{b} \right \backslash`                      |
| 上下箭头                                  | $\left \uparrow \frac{a}{b} \right \downarrow, \left \Uparrow \frac{a}{b} \right \Downarrow,\left \updownarrow \frac{a}{b} \right \Updownarrow$ | `\left \uparrow \frac{a}{b} \right \downarrow`, `\left \Uparrow \frac{a}{b} \right \Downarrow` ,`\left \updownarrow \frac{a}{b} \right \Updownarrow` |
| 混合括号                                  |                                                              |                                                              |
| 使用`\left.`和`\right.`不显示某侧的括号； |                                                              |                                                              |

> **注意**：在 Markdown 当中使用 LaTeX 时，为了避免语法冲突，花括号`{}`必须采用`\{`和`\}`进行转义，或者改用`\lbrace`和`\rbrace`的方式；如果是在 Markdown 表格当中使用 LaTeX，则必须采用 `\vert` 或者 `\Vert` 代替直接在公式当中书写 `|`和`||`。

### 括号尺寸

|                             符号                             | LaTeX                                                        |
| :----------------------------------------------------------: | :----------------------------------------------------------- |
| $( \bigl( \Bigl( \biggl( \Biggl( \dots \Biggr] \biggr] \Bigr] \bigr] ]$ | `( \bigl( \Bigl( \biggl( \Biggl( \dots \Biggr] \biggr] \Bigr] \bigr] ]` |
| $\{ \bigl \{ \Bigl \{ \biggl \{ \Biggl \{ \dots \Biggr\rangle \biggr\rangle \Bigr\rangle \bigr\rangle \rangle$ | `\{ \bigl \{ \Bigl \{ \biggl \{ \Biggl \{ \dots \Biggr\rangle \biggr\rangle \Bigr\rangle \bigr\rangle \rangle` |
|                                                              | \|\|\|\|…\|\|\|\|                                            |
| $\lfloor \bigl\lfloor \Bigl\lfloor \biggl\lfloor \Biggl\lfloor \dots \Biggr\rceil \biggr\rceil \Bigr\rceil \bigr\rceil \rceil$ | `\lfloor \bigl\lfloor \Bigl\lfloor \biggl\lfloor \Biggl\lfloor \dots \Biggr\rceil \biggr\rceil \Bigr\rceil \bigr\rceil \rceil` |
| $\uparrow \big\uparrow \Big\uparrow \bigg\uparrow \Bigg\uparrow \dots \Bigg\Downarrow \bigg\Downarrow \Big\Downarrow \big\Downarrow \Downarrow$ | `\uparrow \big\uparrow \Big\uparrow \bigg\uparrow \Bigg\uparrow \dots \Bigg\Downarrow \bigg\Downarrow \Big\Downarrow \big\Downarrow \Downarrow` |
| $\updownarrow \big\updownarrow \Big\updownarrow \bigg\updownarrow \Bigg\updownarrow \dots \Bigg\Updownarrow \bigg\Updownarrow \Big\Updownarrow \big\Updownarrow \Updownarrow$ | `\updownarrow \big\updownarrow \Big\updownarrow \bigg\updownarrow \Bigg\updownarrow \dots \Bigg\Updownarrow \bigg\Updownarrow \Big\Updownarrow \big\Updownarrow \Updownarrow` |
| $/ \big/ \Big/ \bigg/ \Bigg/ \dots \Bigg\backslash \bigg\backslash \Big\backslash \big\backslash \backslash$ | `/ \big/ \Big/ \bigg/ \Bigg/ \dots \Bigg\backslash \bigg\backslash \Big\backslash \big\backslash \backslash` |

## 空格与换行

| 序号                             | 符号           | LaTeX          |
| :------------------------------- | :------------- | -------------- |
| **双空格**                       | $a \qquad b$   | `a \qquad b`   |
| **单空格**                       | $a \quad b$    | `a \quad b`    |
| **字符空格**                     | $a\ b$         | `a\ b`         |
| **文本模式中的字符空格**         | $a \text{ } b$ | `a \text{ } b` |
| **大空格**                       | $a\;b$         | `a\;b`         |
| **小空格**                       | $a\,b$         | `a\,b`         |
| **极小空格**                     | $ab$           | `ab`           |
| **极小空格**（用于区分语法）     | $a b$          | `a b`          |
| **无空格**（用于区分多字母变量） | $\mathit{ab}$  | `\mathit{ab}`  |

|                 符号                 |                LaTeX                 |
| :----------------------------------: | :----------------------------------: |
| $\displaylines{y=1729x \\ y=1729-x}$ | `\displaylines{y=1729x \\ y=1729-x}` |

## 颜色

LaTeX 默认支持下面表格当中的文本颜色：

![img](G:\study\02-notebook\Zhao-Mingbin.github.io\src\CFD学习\NS方程\media\colors.png)

### 字体颜色

公式当中可以使用`\color{options}{math}`调用颜色命令，第 1 个参数为**颜色**，第 2 个参数为**公式内容**：

|                            符号                             |                            LaTeX                            |
| :---------------------------------------------------------: | :---------------------------------------------------------: |
| ${\color{Blue}x^2}+{\color{Orange}2x}-{\color{LimeGreen}1}$ | `{\color{Blue}x^2}+{\color{Orange}2x}-{\color{LimeGreen}1}` |

### 背景颜色

文本环境中可以使用`\colorbox{options}{text}`来调用背景颜色命令，第 1 个参数为**颜色**，第 2 个颜色为**公式内容**：

|             符号              |             LaTeX             |
| :---------------------------: | :---------------------------: |
| $\colorbox{yellow}{Thistext}$ | `\colorbox{yellow}{Thistext}` |

该命令应用于数学环境当中时，需要在第 2 个参数加入`$\displaystyle + 公式$`：

|                       符号                       |                      LaTeX                       |
| :----------------------------------------------: | :----------------------------------------------: |
| $\colorbox{yellow}{$\displaystyle \frac{a}{b}$}$ | `\colorbox{yellow}{$\displaystyle \frac{a}{b}$}` |

> **注意**：在 Markdown 内联 LaTeX 公式`$...$`当中使用`$\displaystyle + 公式$`语法时将会引发冲突，因此该语法仅用于多行公式 `$$...$$`。

### RGB 颜色

通过使用`\definecolor`命令可以自定义 LaTeX 公式的颜色：

|                             符号                             |                            LaTeX                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| $\definecolor{mygreen}{RGB}{0,200,0} {\color{mygreen}e^{i \pi} + 1 = 0 }$ | `\definecolor{mygreen}{RGB}{0,200,0} {\color{mygreen}e^{i \pi} + 1 = 0 }` |

## 字体

### 字体加粗

| 符号                                      | LaTeX                                     |
| :---------------------------------------- | :---------------------------------------- |
| $\boldsymbol{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\boldsymbol{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\boldsymbol{abcdefghijklmnopqrstuvwxyz}$ | `\boldsymbol{abcdefghijklmnopqrstuvwxyz}` |
| $\boldsymbol{0123456789}$                 | `\boldsymbol{0123456789}`                 |

### 黑体

| 符号                                  | LaTeX                                 |
| :------------------------------------ | :------------------------------------ |
| $\mathbf{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathbf{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathbf{abcdefghijklmnopqrstuvwxyz}$ | `\mathbf{abcdefghijklmnopqrstuvwxyz}` |
| $\mathbf{0123456789}$                 | `\mathbf{0123456789}`                 |

### 黑板报体

| 符号                                  | LaTeX                                 |
| :------------------------------------ | :------------------------------------ |
| $\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathbb{abcdefghijklmnopqrstuvwxyz}$ | `\mathbb{abcdefghijklmnopqrstuvwxyz}` |
| $\mathbb{0123456789}$                 | `\mathbb{0123456789}`                 |

### 斜体

| 符号                                  | LaTeX                                 |
| :------------------------------------ | :------------------------------------ |
| $\mathit{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathit{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathit{abcdefghijklmnopqrstuvwxyz}$ | `\mathit{abcdefghijklmnopqrstuvwxyz}` |
| $\mathit{0123456789}$                 | `\mathit{0123456789}`                 |

### 罗马体

| 符号                                  | LaTeX                                 |
| :------------------------------------ | :------------------------------------ |
| $\mathrm{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathrm{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathrm{abcdefghijklmnopqrstuvwxyz}$ | `\mathrm{abcdefghijklmnopqrstuvwxyz}` |
| $\mathrm{0123456789}$                 | `\mathrm{0123456789}`                 |

### 无衬线体

| 符号                                  | LaTeX                                 |
| :------------------------------------ | :------------------------------------ |
| $\mathsf{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathsf{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathsf{abcdefghijklmnopqrstuvwxyz}$ | `\mathsf{abcdefghijklmnopqrstuvwxyz}` |
| $\mathsf{0123456789}$                 | `\mathsf{0123456789}`                 |

### 手写体

| 符号                                   | LaTeX                                  |
| :------------------------------------- | :------------------------------------- |
| $\mathcal{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathcal{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathcal{abcdefghijklmnopqrstuvwxyz}$ | `\mathcal{abcdefghijklmnopqrstuvwxyz}` |
| $\mathcal{0123456789}$                 | `\mathcal{0123456789}`                 |

### 哥特字体

| 符号                                    | LaTeX                                   |
| :-------------------------------------- | :-------------------------------------- |
| $\mathfrak{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$ | `\mathfrak{ABCDEFGHIJKLMNOPQRSTUVWXYZ}` |
| $\mathfrak{abcdefghijklmnopqrstuvwxyz}$ | `\mathfrak{abcdefghijklmnopqrstuvwxyz}` |
| $\mathfrak{0123456789}$                 | `\mathfrak{0123456789}`                 |

### 小脚本风格

| 符号                                              | LaTeX                                             |
| :------------------------------------------------ | :------------------------------------------------ |
| ${\scriptstyle\text{ABCDEFGHIJKLMNOPQRSTUVWXYZ}}$ | `{\scriptstyle\text{ABCDEFGHIJKLMNOPQRSTUVWXYZ}}` |
| ${\scriptstyle\text{abcdefghijklmnopqrstuvwxyz}}$ | `{\scriptstyle\text{abcdefghijklmnopqrstuvwxyz}}` |
| ${\scriptstyle\text{0123456789}}$                 | `{\scriptstyle\text{0123456789}}`                 |

### 字号尺寸

| 符号                                | LaTeX                               |
| :---------------------------------- | :---------------------------------- |
| ${\tiny abc极小tiny}$               | `{\tiny abc极小tiny}`               |
| ${\scriptsize abc 超小 scriptsize}$ | `{\scriptsize abc 超小 scriptsize}` |
| ${\small abc 小 small}$             | `{\small abc 小 small}`             |
| ${\normalsize abc 正常 normal}$     | `{\normalsize abc 正常 normal}`     |
| ${\large abc 大 large}$             | `{\large abc 大 large}`             |
| ${\Large abc 超大 Large}$           | `{\Large abc 超大 Large}`           |
| ${\LARGE abc 特大 LARGE}$           | `{\LARGE abc 特大 LARGE}`           |
| ${\huge abc 巨大 huge}s$            | `{\huge abc 巨大 huge}s`            |
| ${\Huge abc 巨无霸 Huge}$           | `{\Huge abc 巨无霸 Huge}`           |

```python
#格式转化脚本
def convert(text,*arg):
    print('start******************************\n')
    raw = text.split('\n')
    #print(raw)
    for i in range(2,len(raw)):
        every = raw[i].split('|')
        for num in arg:
            #print(num)
            format = every[num+1].strip()[1:-1] 
            if format == '':
                format = ' '
                every[num] = f"{format}"
            else:
                every[num] = f"${format}$" #第一个参数
        #print(every)#第二个参数
        new_every="|".join(every)
        raw[i] = new_every
    new_raw = "\n".join(raw)
    return new_raw
text2 = pp.paste()
pp.copy(convert(text2,1))
```

@来源：[通用 LaTeX 数学公式语法手册 | Bit by bit (gitee.io)](https://uinika.gitee.io/Zen/LaTex/)
