---
title: "Tutorial 2 e 3"
description: "Tentando ficar em dia"
pubDate: "2025-03-26"
heroImage: "/post_img.webp"
---

Faltei na aula do dia 19, então acabei terminando o tutorial 2 e começando o tutorial 3 na aula do dia 26. 

Probleminhas no tutorial 2: Fiz uma confusão com os nomes das partições, especialmente com os sdaX. Fiquei um pouco travada na parte final, durante o mount do rootfs, mas depois de conversar com o monitor consegui resolver.

Comecei a entender melhor qual vai ser o foco da disciplina — onde e como vamos modificar o kernel do Linux. A ideia de alterar módulos que podem ser montados e desmontados (removidos com rmmod) começou a fazer mais sentido.

Probleminhas no tutorial 3: Eu não sabia que não era uma boa ideia usar clear quando surgem erros relacionados aos módulos. Acabei executando e isso dificultou um pouco o diagnóstico do que tinha dado errado. Quando tentei carregar os módulos de novo, demorou bastante, e só depois entendi que seria melhor ter analisado os erros primeiro (com dmesg, por exemplo) antes de limpar a tela @-@