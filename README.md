Aalen model
===================

This program will calculate some statistics related with Aalen model.

We know Cox proportional hazard model is a very popular model in applications, especially in medical research.
Actually, additive hazard model is  an important alternative to the proportional hazards model, which assumes that the covariates act in an additive manner on an unknown baseline hazard rate. That is:

                                      h(t|z)=h0(t)+b(t)'z(t)
                                      
Related models have been investigated by Aalen (1980, 1989), Huffer and McKeague (1991), Lin and Ying (1994), Lin and Ying
(1995), and McKeague and Sasieni (1994), among others. In particular, Lin and Ying (1994)
proposed a score-type function to obtain an estimator of 0 in an analytic form.


Usage
==========
Pharynx data comes from a clinical trial carried out by the Radiation Therapy Oncology Group in the United States, and
concern treatment of carcinoma of the oropharynx. Survival time from diagnosis is given in days and some of the patients are censored. Data are given for 195 patients, two of whom are not included in the analysis due to missing
values.


tdata=pharynx[-c(136,159),]  #去掉两个异常值

p=7

jg=aalen(tdata,p,2) 

u=jg[[3]][2:(p+1)]  

v=jg[[4]][2:(p+1),2:(p+1)] 

tst=u/sqrt(diag(v));tst  

[1] -1.6247545  0.9289796 -1.4147887  0.2861529  4.1429450  2.5158461  1.9815236


This result is identical to Aalne(1989)' paper, and estimated cumulative regression functions are shown for the covariates "sex", "condition","T-stage" and "N-stage" in following figures







