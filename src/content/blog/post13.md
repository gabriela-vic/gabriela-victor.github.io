---
title: "Complementando nossa contribuição"
description: ""
pubDate: "2025-05-14"
#heroImage: "/post_img.webp"
---
 Como dito no post passado, encontramos a origem do problema da issue #327 do app Weather em um arquivo usado pela biblioteca ligbweather, utilizada no cõdigo do app. Disso, tivemos a ideia de fazer com que o o aplicativo informasse verbalmente e visualmente ao usuário que houve um erro na obtenção de informações sobre a localidade escolhida.

 Primeiro, fizemos com que uma caixa de mensagem aparecesse na tela, sobre a janela do aplicativo, informando o erro. Essa caixa conta com dois botões, um que fecha a caixa e outro que oferece ao usuãrio a opção de reportar o problema. Ao selecionar esta última opção, o cliente ẽ redirecionado ao site do gnome gitlab onde pode abrir uma nova issue relacionada ao erro.

 Depois, após algum tempo quebrando a cabeça, conseguimos fazer com que um traço fosse mostrado no lugar da temperatura 0 graus, o que acreditamos ser mais apropriado e user friendly do que mostrar uma temperatura. Usamos um mẽtodo chamado isValid()

 Por fim, achamos um ícone da biblioteca gtk (biblioteca de imagens do gnome) para substituir o ícone anterior que era uma figura de uma lua, representando um noite sem chuva. Escolhemos um ícone tipo "warning", um triângulo com um ponto de exclamação dentro.

Fizemos mais alguns ajustes, como fazer com que a caixa de mensagem do erro não desapareça sem que o usuário clique em "fechar" e deixar o cõdigo mais organizado.

Com isso, estamos prontas para fazer um novo merge request.