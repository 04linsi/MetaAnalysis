

# 连续型变量

## 森林图

Of binary ond Continuous(metan)

metan var3 var4 var5 var6 var7 var8, label(namevar=var1, yearvar=var2) random nostandard

## 亚组分析

. metan var3 var4 var5 var6, label(namevar=var1, yearvar=var2) by(var1) random nostandard

## 敏感性分析

metaninf

metaninf var3 var4 var5 var6 var7 var8, label(namevar=var1, yearvar=var2) fixed cohen

## 发表偏倚

### egger

 metabias _ES _seES, egger graph

### begg

metabias _ES _seES, begg

## 漏斗图

metafunnel _ES _seES

## Meta回归

回归过程中变量只能是数字

metareg _ES var2 var10 var12, wsse(_seES) bsest(reml)





# 二分类变量

## 森林图

metan var3 var4 var5 var6, label(namevar=var1, yearvar=var2) fixed rr



## 亚组分析

metan var3 var4 var5 var6, label(namevar=var1, yearvar=var2) by(var7) fixed rr

## 敏感性分析

 metaninf var3 var4 var5 var6, label(namevar=var1, yearvar=var2) fixed rr

## 发表偏倚

首先切换数据为log

gen logRR=log(_ES)

### egger

 metabias logRR _selogES , egger graph

### begg

metabias logRR _selogES, begg

## 漏斗图

. metafunnel logRR _selogES

## Meta回归

回归过程中变量只能是数字

 metareg logRR var2 var8 var10, wsse(_selogES) bsest(reml)

