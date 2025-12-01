---
layout: post
title: "Coffee Notes en 2025"
date: 2025-11-30 19:00 -0300
categories: es
image: https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/coffee_notes_post.png
tags: [coffee-notes, swift]
---

Ya pasó alrededor de un año desde que les comenté sobre mi sideproject [Coffee Notes](https://apps.apple.com/ar/app/coffee-notes-by-fecapp/id6449650317?l=en-GB) y se me ocurrió que era un buen momento para hacer un repaso de todos los cambios que hubo en el 2025. Allá vamos.

# Sección de Comunidad
Posiblemente la parte que más me demandó esfuerzo haya sido la sección de "Comunidad": una pantalla con un carrousel de mapas de distintas ciudades con puntos que indican dónde los usuarios estuvieron tomando café, junto con algunas métricas derivadas de la app.

Me gusta la idea de hacer check-ins en cafeterías porque me permite ver qué tanto movimiento tiene la app y entender qué lugares para tomar café son los más populares. Lamentablemente, no enganchó mucho este concepto. ¡Pensar que esa idea fue FUROR en FourSquare hace 10 años! Por un lado me parece que pasó de moda pero también creo que fallé en generar un verdadero incentivo al usuario.

<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/community-tab.gif" loading="lazy" alt="Community Tab" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/profile.gif" loading="lazy" alt="Profile Tab" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/leaderboard.png" loading="lazy" alt="Leaderboard screen" />
  </div>
  <em>Pantallas de Community, Profile y Leaderboard.</em>
</div>

Armé un leaderboard para gamificar la experiencia: los usuarios que hacen check-in o recomiendan cafeterías ganan puntos. El problema es que me quedé a mitad de camino: los puntos no se canjean por NADA más que "fama y gloria", tampoco hay stickers ni badges que se desbloquean... ni siquiera hay un sonido de trompetas con una animación de confetti cada vez que hacés check-in. Es un flow que necesita apremiar al usuario de alguna manera y creo que no lo está haciendo bien.

Por otra parte agregué métricas:
- ¿Qué ciudad obtiene más check-ins?
- ¿Qué cafetería obtiene más check-ins?
- ¿Qué ciudad o país tiene más cafeterías registradas?

<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/community-tab-charts.png" loading="lazy" alt="Charts in Community Tab" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/cities.png" loading="lazy" alt="Cities with more coffee shops registered" />
  </div>
  <em>Gráficos derivados de los datos agregados por los usuarios</em>
</div>

Esto la verdad fue bastante fácil de hacer y una linda excusa para probar [Swift Charts](https://developer.apple.com/documentation/Charts).

# Notes Tab
Agregué la posibilidad de ordenar las notas por Rating. Una pavada pero me resultó muy útil después de 1 año de estar coleccionando apuntes sobre cafés.

# Cambios invisibles
- Bug fixes.
- Adoptar Liquid Glass.
- Cambios sutiles en la UI/UX.
- Cambios en el server.

Son cosas que pasan desapercibidas pero necesarias para pavimentar los cambios futuros y para que yo pueda dormir a la noche :-)

# Métricas de uso en 2025
<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/appstore-connect.png" loading="lazy" alt="Screenshot of the AppStore Connect Analytics" />
  </div>
  <em>Hacer una app es fácil. Hacer una app popular... esa es otra historia.</em>
</div>

Los resultados fueron... mediocres. 344 descargas en un año. Durante algunos meses pagué publicidad en el AppStore de Apple, eso disparó mis números de impresiones y Page Views que impactaron un poco en las descargas pero no tanto como para justificar el gasto.

# Aprendizajes
Por un lado, no recomiendo hacer apps que dependan del volumen de usuarios. La idea que los usuarios suban data de cafeterías y hagan check-in voluntariamente a cambio de ✨ **PUNTITOS** ✨ en 2025 para una app indie... es casi delirante.

Por otro, sugiero que elijan un scope MUY chico y no salgan de ahí. Coffee Notes es 2 apps en una: directorio de cafeterías y una app para tomar notas de café. Esa dualidad a veces me juega en contra porque me es difícil explicar el producto y a veces pierdo foco muy facilmente.

# 2026
Creo que vengo sonando muy negativo así que voy a aclarar algo: voy a seguir trabajando en Coffee Notes el año que viene, tengo un roadmap ENTERO de cosas que quiero hacer.

Hacer esta app me llena de satisfacción como programador porque puedo mostrarle al mundo mis skills. También me sirve para practicar y probar frameworks que en mi trabajo habitual no tengo oportunidad. Por otra parte es la app que me gustaría tener como fanático del café y espero que lo sea para ustedes también <3

# Links
- [Project Post: Coffee Notes](https://www.betzerra.com/project/coffee-notes)
- [AppStore: Coffee Notes](https://apps.apple.com/ar/app/coffee-notes-by-fecapp/id6449650317?l=en-GB)
- [Swift Charts](https://developer.apple.com/documentation/Charts)
- [Showcase:​ Learn how apps are integrating the new design and Liquid Glass | Meet with Apple
](https://www.youtube.com/watch?v=hyFIakdwi9Y)