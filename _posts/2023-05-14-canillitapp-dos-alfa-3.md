---
layout: post
title: CanillitappDos v0.3 (alpha) - CoreML
date: 2023-05-14 13:21 -0300
categories: es
image: https://nyc3.digitaloceanspaces.com/betzerra/blog/2023/05/14/canillitapp_0_3.png
tags: [canillitapp]
---

Otro update que salió bastante más rápido de lo que esperaba.

Hasta ahora las noticias se clasificaban de acuerdo a su URL: algunos medios de noticias ponen como prefijo la palabra _"economia"_, _"politica"_, _"tecno"_, etc; pero muchos otros medios no.

Lo que hice fue usar esa información para entrenar un modelo de Machine Learning y poder predecir las noticias que no estaban categorizadas de origen.

Es impresionante cómo Apple creó herramientas tan fáciles de usar, pude lograr esto teniendo conocimientos prácticamente nulos de machine learning. De ahora en más, cuando vean una categoría que empieza con "🤖" como prefijo es porque esa categoría fue adivinada por ML.

Un abrazo ayer a los que me dieron consejos de UX en este [thread](https://twitter.com/betzerra/status/1657575540486819840?s=61&t=TTlOq-XHR1gPyDajSS2ovw) para este feature. Es muy posible que cambie el "🤖" por "✨" o haga algo más complejo como sugirió Nico pero soy ansioso y quiero sacar esta release tal como está.

Pueden bajar la nueva versión para **macOS** con este [link](https://nyc3.digitaloceanspaces.com/betzerra/blog/2023/05/14/canillitapp-dos-2023-05-14.zip)

## Links
Algunos links que usé para aprender a hacer este release:
- [Apple Developer - Introducing the Create ML App](https://developer.apple.com/videos/play/wwdc2019/430/)
- [Apple Developer - Training Text Classifiers in Create ML](https://developer.apple.com/videos/play/wwdc2019/428/)
- [Importing and Exporting Files in SwiftUI](https://betterprogramming.pub/importing-and-exporting-files-in-swiftui-719086ec712)