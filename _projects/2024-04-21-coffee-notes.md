---
title: Coffee Notes
date: 2024-04-21 23:30:00 -0300
subtitle: 2024 - PRESENT
image: https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/coffee-notes-thumbnail.png
---

# TLDR;
Hice una app sobre café para iOS, iPadOS y macOS, podés bajarla en el [App Store](https://apps.apple.com/ar/app/coffee-notes-by-fecapp/id6449650317?l=en-GB).

Para los que tienen Android, hay una [versión web](https://www.feca.app) con features reducidas hecha por [Tomás Millán](https://www.tomasm.site).

# "¿No habías hecho una app sobre café antes?"
**[Coffee Notes](https://www.feca.app)** vendría a ser el sucesor de [Fecapp](./fecapp.html) con varios cambios:

1. **El backend está programado en [Swift](https://www.swift.org) usando [Vapor](https://vapor.codes).** El context switch que tenía entre el cliente y el servidor disminuía mucho mi productividad, especialmente porque venía de usar [Ruby on Rails](https://rubyonrails.org) donde el framework hace mucha magia y hay que recordar muchas convenciones.

2. **La app no está enfocada en Buenos Aires sino que escala a más ciudades.** Honestamente no recuerdo porqué me limité a Buenos Aires cuando hice la app anterior 🤦‍♂️.

3. **Check-Ins!** Los usuarios pueden registrar qué cafeterías visitan. La idea es usar esto como un componente "social", generar engagement y poder usar esa información para saber qué cafeterías son tendencia. _"¿Se acuerdan de Foursquare y Yelp?"_

4. **Notas de cata.** Esta fue la idea original de la app (los puntos anteriores fueron un intento de consolidar las 2 apps en una): poder documentar los distintos cafés que tomo para poder entender mis mejor mis preferencias y comprar mejor café luego.

# Directorio de cafeterías y tostadores
Como mencioné anteriormente, esta es la segunda vez que creo una app que funciona como un directorio de cafeterías.

Creo que los cimientos de este backend están más firmes que su antecesor (para empezar, este backend SI tiene unit tests 🤣) y espero que no necesite refactors en el medio plazo.

La base de datos es colaborativa: cada cafetería y tostador puede ser sugerida por los usuarios (incluso aquellos que no están registrados). Es tarea de los administradores revisar los registros y aprobarlos, rechazarlos.

También es posible sugerir café tostados y asignarlos a un tostador. Me interesa tener una base de datos global de cafés tostados y poder analizar qué tendencias aparecen en el tostado de café.

<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/home-low.png" loading="lazy" alt="Home Screen" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/coffee-shop-detail-low.png" loading="lazy" alt="Coffee Shop detail screen" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/roaster-flow.gif" loading="lazy" alt="Roaster UX Flow" />
  </div>
  <em>Directorio de cafeterías y tostadores</em>
</div>

# Coffee Notes?
El problema específico que quería resolver esta vez era poder tomar notas de los cafés que me gustaban (y los que no), para luego estar mejor informado a la hora de comprar café. Entender mis gustos ¿prefiero lavado o natural? ¿Colombia o Brasil?

Para agregarle un poco de engagement agregué un feature para compartir una "tarjetita" de review que puede ser posteada en Instagram.

<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/notes-low.png" loading="lazy" alt="Notes Screen" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/notes-detail-low.png" loading="lazy" alt="Notes detail view" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/notes-share-low.png" loading="lazy" alt="Share notes" />
  </div>
  <em>Notas de cata</em>
</div>

# Check-Ins
Recientemente agregué la posibilidad de hacer check-in en cafeterías, de esta manera poder inferir qué regiones y cafeterías tienen más engagament con la app.

<div class="gallery-box">
  <div class="gallery">
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/check-in-detail-low.png" loading="lazy" alt="Check-In" />
    <img src="https://nyc3.digitaloceanspaces.com/betzerra/blog/projects/coffee-notes/community-low.png" loading="lazy" alt="Community" />
  </div>
  <em>Check-Ins y Comunidad</em>
</div>

