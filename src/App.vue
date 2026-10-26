<script setup>
</script>

<template>
  <div class="pagina">
    <header class="encabezado">
      <a class="logo" href="#">
        <span class="logo-icono">🌎</span>
        <span>Country Explorer</span>
      </a>

      <span class="etiqueta">Explora el mundo</span>
    </header>

    <main class="contenido">
      <section class="presentacion">
        <span class="subtitulo">DESCUBRE EL MUNDO</span>

        <h1>Explorador de Países</h1>

        <p>
          Conoce países de todo el mundo, sus capitales,
          regiones y datos interesantes.
        </p>

        <div class="buscador">
          <span class="buscador-icono">⌕</span>
          <input
            type="text"
            placeholder="Buscar un país..."
            aria-label="Buscar un país"
            disabled
          />
          <span class="buscador-ayuda">Próximamente</span>
        </div>
      </section>

      <section class="seccion-paises">
        <div class="seccion-titulo">
          <div>
            <h2>Países destacados</h2>
            <p>Una pequeña muestra de nuestro planeta.</p>
          </div>

          <span class="contador">03 países</span>
        </div>

        <div class="grid-paises">
          <article class="tarjeta-pais">
            <div class="bandera bandera-canada">🇨🇦</div>

            <div class="datos-pais">
              <span class="codigo-pais">CA</span>
              <h3>Canadá</h3>
              <p class="nombre-ingles">Canada</p>

              <div class="detalle">
                <span>Capital</span>
                <strong>Ottawa</strong>
              </div>

              <div class="detalle">
                <span>Región</span>
                <strong>América</strong>
              </div>

              <div class="detalle">
                <span>Población</span>
                <strong>40,097,761</strong>
              </div>
            </div>
          </article>

          <article class="tarjeta-pais">
            <div class="bandera bandera-japon">🇯🇵</div>

            <div class="datos-pais">
              <span class="codigo-pais">JP</span>
              <h3>Japón</h3>
              <p class="nombre-ingles">Japan</p>

              <div class="detalle">
                <span>Capital</span>
                <strong>Tokio</strong>
              </div>

              <div class="detalle">
                <span>Región</span>
                <strong>Asia</strong>
              </div>

              <div class="detalle">
                <span>Población</span>
                <strong>123,753,041</strong>
              </div>
            </div>
          </article>

          <article class="tarjeta-pais">
            <div class="bandera bandera-brasil">🇧🇷</div>

            <div class="datos-pais">
              <span class="codigo-pais">BR</span>
              <h3>Brasil</h3>
              <p class="nombre-ingles">Brazil</p>

              <div class="detalle">
                <span>Capital</span>
                <strong>Brasilia</strong>
              </div>

              <div class="detalle">
                <span>Región</span>
                <strong>América</strong>
              </div>

              <div class="detalle">
                <span>Población</span>
                <strong>212,583,750</strong>
              </div>
            </div>
          </article>
        </div>
      </section>

      <footer class="pie">
        <span>🌐 Explorador de Países</span>
        <span>Proyecto académico · Vue 3</span>
      </footer>
    </main>
  </div>
</template>