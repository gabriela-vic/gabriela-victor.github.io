---
title: "Primeira contribuição no Kernel Linux"
description: "Resolvendo um problema de funções duplicadas"
pubDate: "2025-04-09"
heroImage: "/post_img.webp"
---

Finalmente começamos nossa jornada de contribuições no Kernel Linux! Vamos trabalhar em drivers do subsistema IIO (Industrial I/O).

Eu e minha dupla, Beatriz Viana, escolhemos resolver um problema de duplicação no driver zopt2201, que é responsável por um sensor que mede a intensidade da luz ambiente (ALS) e radiação ultravioleta B (UVB).

Analisando o código, encontramos duas funções — zopt2201_write_scale_als_by_idx e zopt2201_write_scale_uvb_by_idx — que tinham implementações praticamente idênticas. A única diferença era o vetor que cada uma deveria manipular: uma mexia no als e a outra no uvb. Mas percebemos que a função do uvb estava, na verdade, acessando os campos do vetor errado (als).

Pra resolver isso, criamos uma função genérica que evita essa duplicação e recebe como parâmetro o vetor correto a ser modificado. Também ajustamos a struct usada nos arrays de escala, renomeando para zopt2201_scale, pra poder reutilizá-la nas duas situações.

Nos próximos dias, vamos focar em preparar e enviar o patch seguindo as instruções que recebemos em aula.