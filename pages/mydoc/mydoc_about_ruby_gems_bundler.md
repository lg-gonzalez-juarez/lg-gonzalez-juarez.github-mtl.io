---
title: Notas Matlab
tags: [getting_started]
keywords:
summary: ""
sidebar: mydoc_sidebar
permalink: mydoc_about_ruby_gems_etc.html
folder: mydoc
---

## About Matlab Commands

### Ecuaciones simbolicas
```matlab

%{
L=zeros(5); %L(i,j)=(fila,columna)  
L(1,1)=d.Ld;       L(1,2)=d.Lad;     L(1,3)=d.Lad;
L(2,1)=d.Lad;     L(2,2)=d.Lffd;      L(2,3)=d.Lfkd;
L(3,1)=d.Lad;     L(3,2)=d.Lfkd;   L(3,3)=d.Lkkd;
L(4,4)=d.Lq;       L(4,5)=d.Laq;
L(5,4)=d.Laq;    L(5,5)=d.Lkkq;
%}

syms id ifd ikd iq ikq i0
syms Ld Lmd Lq Lmq Lls Lff Lkdkd Lkqkq

%{
... sistema de 6x6
i=[id;iq;i0;ifd;ikd;ikq]  
L=[Ld 0 0 Lmd Lmd 0;...
    0 Lq 0 0 0 Lmq;...
    0 0 Lls 0 0 0;...
    Lmd 0 0 Lff Lmd 0;...
    Lmd 0 0 Lmd Lkdkd 0;...
    0 Lmq 0 0 0 Lkqkq];
%}

... sistema de 5x5
i=[id;iq;ifd;ikd;ikq]  
L=[Ld 0  Lmd Lmd 0;...
    0 Lq 0 0 Lmq;...
    Lmd 0 Lff Lmd 0;...
    Lmd 0 Lmd Lkdkd 0;...
    0 Lmq 0 0 Lkqkq]

flux=L*i

... Eq tension estator
dPsid=d.w_base*(vd+Psiq*wr-d.Ra*id);   
dPsiq=d.w_base*(vq-Psid*wr-d.Ra*iq);   
dPsi0=d.w_base*(v0+d.Ra*i0);
... Eq tension rotor
dPsifd=d.w_base*(vfd-d.Rfd+ifd);    
dPsikd=d.w_base*(vkd-d.Rkd*ikd);
dPsikq=d.w_base*(vkq-d.Rkq*ikq);
Te=(3/2)*p*Psid*iq-Psiq*id;
dwr=(Tm-Te)/(2*d.H);
```


###
## Parámetros de la máquina 

`D:\wk_matlab\uc3m\mt\pc104\MTLB\src\Motors\SYNgnrt\StateStable`


- D:\wk_matlab\uc3m\mt\pc104\MTLB\src\Motors\SYNgnrt\StateStable_ok2021



### Inicialización de la máquina sincrona


`D:\wk_matlab\uc3m\mt\pc104\MTLB\src\Motors\SYNgnrt\MySyncGnrt\model_ok_Junio2011`

finalmente encontrado y operativo
`D:\wk_matlab\uc3m\mt\pc104\MTLB\src\Motors\SYNgnrt\MySyncGnrt\model_ok_Junio2011_ok2021`


### Diseño del sistema de control

revisar estos archivos
`D:\wk_matlab\uc3m\mt\pc104\MTLB\src\Motors\SYNgnrt\CheeMunOng`


Este es el folder bueno que usamos para los italianos

`D:\wk_matlab\uc3m\mt\pc104\MTLB\src\Motors\SYNgnrt\Kundur `


{% include links.html %}
