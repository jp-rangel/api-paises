<script setup>
import { ref, onMounted } from 'vue'

const paises = ref([])

onMounted(async () => {
  try {
    const respuesta = await fetch(
      'https://api.restcountries.com/countries/v5?limit=100',
      {
        headers: {
          Authorization: 'rc_live_b20ec7e6b3f94a1199bf168ba11ebd26'
        }
      }
    )

    const cuerpo = await respuesta.text()

    console.log('Estado HTTP:', respuesta.status)
    console.log('Respuesta de REST Countries:', cuerpo)

    if (!respuesta.ok) {
      throw new Error(`La API respondió HTTP ${respuesta.status}`)
    }

    const resultado = JSON.parse(cuerpo)
    paises.value = resultado.data.objects
  } catch (error) {
    console.error('Error al consultar los países:', error)
  }
})
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
            <h2>Países del mundo</h2>
            <p>Información obtenida desde REST Countries.</p>
          </div>

          <span class="contador">
            {{ paises.length }} países
          </span>
        </div>

        <div class="grid-paises">
          <article
            v-for="pais in paises"
            :key="pais.codes.alpha_3"
            class="tarjeta-pais"
          >
            <div class="bandera">
              <img
                v-if="pais.flag?.url_png"
                :src="pais.flag.url_png"
                :alt="`Bandera de ${pais.names.common}`"
                class="imagen-bandera"
              />
              <span v-else>🏳️</span>
            </div>

            <div class="datos-pais">
              <span class="codigo-pais">
                {{ pais.codes.alpha_2 }}
              </span>

              <h3>{{ pais.names.translations.spa.common }}</h3>

              <p class="nombre-oficial">
                {{ pais.names.translations.spa.official }}
              </p>

              <div class="detalle">
                <span>Capital</span>
                <strong>
                  {{ pais.capitals?.[0]?.name || 'No disponible' }}
                </strong>
              </div>

              <div class="detalle">
                <span>Región</span>
                <strong>{{ pais.region }}</strong>
              </div>

              <div class="detalle">
                <span>Población</span>
                <strong>
                  {{ pais.population?.toLocaleString('es-MX') ?? 'No disponible' }}
                </strong>
              </div>
            </div>
          </article>
        </div>
      </section>

      <footer class="pie">
        <span>🌐 Explorador de Países</span>
        <span>Proyecto Unidad 3</span>
      </footer>
    </main>
  </div>
</template>