---
title: "Começando a trabalhar no gnome"
description: "Alguns probleminhas"
pubDate: "2025-05-12"
#heroImage: "/post_img.webp"
---
Nos últimos dias, começamos nossa investigação no código do aplicativo Weather com o intuito de achar o que causa o erro na temperatura retornada pelo app para a cidade São Bernardo do Campo. O primeiro passo foi entender como o app faz para obter as informações meteorológicas de um dado local: Uma requisição é feita ao site met.no (portal oficial do Instituto Meteorológico da Noruega) com as coordenadas do local para o qual deseja-se obter os dados (latitude e longitude).

Identificamos que a requisição para São Bernardo do Campo está sendo feita com coordenadas inválidas: latitude =-23.6938 e longitude=-565.46. O valor da longitude deve estar no intervalo [-180, 180]. Além disso, as coordenadas de São Bernardo do Campo são, na verdade, 23.7 graus (latitude) e -46.55 graus (longitude).

Continuando nossa investigação, observamos que a função get_coords() da biblioteca Gweather é usada no app para obter as coordenadas de um local. Então, fomos até o repositóro dessa biblioteca e encontramos a função location_ref_for_idx no arquivo gweather-location.c. Essa função é a que seta os valores de uma localização utilizando um arquivo de referência localizado no diretório data do repositório: Locations.xml. Nesse arquivo, encontramos as coordenadas de São Bernarndo do Campo com valores os incorretos. Usamos o site https://www.gps-coordinates.net/ para pegar as coordenadas corretas e realizar a correção. Realizamos um merge request.

Como encontramos esse problema em uma biblioteca diferente, minha parceira Beatriz Viana abriu uma issue no gitlab Gnome na biblioteca libgweather (#325) informando sobre esses valores incorretos retornados pela biblioteca. Existem outras localidades com o mesmo problema. Temos a ideia de ajustar o app nos próximos dias para que ele lide melhor com valores incorretos (mostrar ao usuário que um erro aconteceu) e não apenas devolva uma temperatura igual a zero. 



