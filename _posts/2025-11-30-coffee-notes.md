---
layout: post
title: "Coffee Notes en 2025"
date: 2025-11-30 19:00 -0300
categories: es
image: https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/coffee_notes_post.png
tags: [coffee-notes, swift]
---

Ya pasó alrededor de un año desde que les comenté sobre mi sideproject [Coffee Notes](https://www.betzerra.com/project/coffee-notes) y se me ocurrió que era un buen momento para hacer un repaso de todos los cambios que hubo en el 2025.

# Community Tab
Todavía estoy buscándole la vuelta a los check-ins. Fueron furor en FourSquare hace 10 años y son una buena métrica para entender qué cafeterías son las más populares pero ya nadie los usa. En parte porque no hay incentivos para hacerlo.

<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/community-tab.gif" loading="lazy" alt="Community Tab" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/profile.gif" loading="lazy" alt="Profile Tab" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/leaderboard.png" loading="lazy" alt="Leaderboard screen" />
  </div>
  <em>Pantallas de Community, Profile y Leaderboard.</em>
</div>

Se me ocurrió gamificar la experiencia poniendo un mapa comunitario donde se vean todos los check-ins (de forma anónima) y armar un leaderboard pero me parece que quedó a mitad de camino. Más allá de aparecer en un ranking, no había premio: los puntos no se canjean por premios, tampoco hay stickers ni badges que se desbloqueen, ni siquiera puse hay un sonido de trompetas con una animación de confetti después de un check-in. ¿Los resultados? solamente 8 usuarios usaron este feature.

Por otra parte están las métricas:
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

Eso también está público en Community Tab y fue una buena excusa para aprender [Swift Charts](https://developer.apple.com/documentation/Charts).

# Notes Tab
Agregué la posibilidad de ordenar las notas por Rating. Una pavada pero me resultó muy útil después de 1 año de estar coleccionando apuntes sobre cafés.

# Cambios invisibles
Bug fixes, cambios sutiles en la UI/UX, cambios en el server, son cosas que pasan desapercibidas pero necesarias para pavimentar los cambios futuros y para que yo pueda dormir a la noche.

# Métricas de uso en 2025
<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/2025/11/30/appstore-connect.png" loading="lazy" alt="Screenshot of the AppStore Connect Analytics" />
  </div>
  <em>Hacer una app es fácil. Hacer una app popular... esa es otra historia.</em>
</div>

Los resultados fueron... mediocres. 344 descargas en un año. Durante algunos meses pagué publicidad en el AppStore de Apple, eso disparó mis números de impresiones y Page Views que subieron un poco las descargas pero no tanto como para justificar el gasto.

# Aprendizajes
No recomiendo hacer apps que dependen del volumen de usuarios. La idea que los usuarios suban data de cafeterías y hagan check-in voluntariamente de ✨ **PUNTITOS** ✨ en 2025 para una app indie... es casi delirante.

Para mi próximo proyecto tendría un scope más chico todavía, Coffee Notes es 2 apps en una: directorio de cafeterías y una app para tomar notas de café. Esa dualidad a veces me juega en contra porque me es difícil explicar el producto y a veces pierdo foco en dónde poner energía.

# 2026
Si bien soné algo negativo en los puntos anteriores, no tengo dudas que voy a seguir trabajando en Coffee Notes el año que viene: tengo un roadmap ENTERO de cosas que quiero hacer. Hacer esta app me llena de satisfacción como programador porque puedo mostrarle al resto mis skills y también puedo practicarlos. Y por otra parte es la app que me gustaría tener como fanático del café, espero que lo sea para ustedes también.

# Links
- [Swift Charts](https://developer.apple.com/documentation/Charts)
- [Showcase:​ Learn how apps are integrating the new design and Liquid Glass | Meet with Apple
](https://www.youtube.com/watch?v=hyFIakdwi9Y)