# Econometrics
University, Uncovered Interest Parity

clear all
clc

MyPath = 'D:\University\master NU\Advanced econometrics\Day 3\forwards\';
[UI] = xlsread([MyPath,'Exchange.xlsx']);

log_s=log(UI(2:end,1)) - log(UI(1:end-1,1));
log_f=log(UI(1:end-1,2)) - log(UI(1:end-1,1));

tbl=[log_f log_s];
T=array2table(tbl);
l=fitlm(T,'linear');

% t=0.8094/(0.8094*1.0633)=0.9404 => beta is not statistically diff from 1
