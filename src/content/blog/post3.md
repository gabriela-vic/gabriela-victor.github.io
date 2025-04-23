---
title: "Iniciando o tutorial 1"
description: "Primeiros problemas..."
pubDate: "2025-03-12"
heroImage: "/post_img.webp"
---
Iniciei os tutorias atrasada por ter conseguido o notebook depois.

Achei os tutoriais fáceis de seguir… na teoria. Mas na prática, vários probleminhas inesperados podem aparecer quando rodamos os comandos na máquina. Às vezes é algo da configuração local, outras vezes um erro de digitação — e como são muitos passos, dá pra ficar meio perdida fácil.

No meu caso, o SSH nem estava instalado corretamente na máquina, e demorei um pouco pra perceber isso. Depois que resolvi, editei o arquivo sshd_config pra permitir login como root sem senha. Mas ao tentar rodar dpkg-reconfigure, recebi um erro dizendo que rescue-ssh.target is disabled or static e que o systemctl não podia ser executado. Isso aconteceu porque eu estava num ambiente onde o systemd não estava ativo, como acontece em chroot ou em ambientes de recuperação. No fim, bastou reiniciar a máquina e as configurações funcionaram normalmente.