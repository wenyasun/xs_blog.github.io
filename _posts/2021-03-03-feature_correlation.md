---
layout: post
author: wenya
title: 如何计算feature间correlation
---
## numeric features(or categorical feature of 2):
 - dataframe.corr() 
 - 此方法默认计算变量间的person correlation
## numeric feature & categorical feature more than 2
 - 可使用scipy.stats.f_oneway方法, the higher the score, the closer the correlation
  '''
  num1=np.random.normal(loc=90,scale=5,size=100)
df1=pd.DataFrame(num1,columns=['Salary'])
df1['Type']='EmpType1'

num2=np.random.normal(loc=70,scale=5,size=100)
df2=pd.DataFrame(num2,columns=['Salary'])
df2['Type']='EmpType2'

num3=np.random.normal(loc=50,scale=5,size=100)
df3=pd.DataFrame(num3,columns=['Salary'])
df3['Type']='EmpType3'

df=pd.concat([df1,df2,df3],axis=0)

from scipy import stats

F, p = stats.f_oneway(df[df.Type=='EmpType1'].Salary,
                      df[df.Type=='EmpType2'].Salary,
                      df[df.Type=='EmpType3'].Salary)

print(F)
  '''
  