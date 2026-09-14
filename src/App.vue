<script setup>
const activities = [
  {
    code: 'G46520201',
    label: 'Venta al por mayor de teléfonos y equipos de comunicación',
    note: ' — actividad principal de Memos',
    main: true,
  },
  { code: 'G46510101', label: 'Venta al por mayor de computadoras y equipo periférico' },
  {
    code: 'H53100002',
    label: 'Servicios de distribución y entrega de correspondencia y paquetes (transporte propio o público)',
  },
  {
    code: 'S95110101',
    label:
      'Reparación y mantenimiento de computadoras, servidores, unidades de almacenamiento, impresoras y periféricos informáticos',
  },
]
</script>

<template>
  <header>
    <h1>MEMOS</h1>
    <p>Emilio Josué Mosquera Rodríguez — Persona Natural | Portafolio comercial verificado ante el SRI</p>
    <span class="badge">● RUC ACTIVO</span>
  </header>

  <main>
    <section class="card">
      <h2>Datos del contribuyente</h2>
      <dl class="grid">
        <div class="field"><dt>RUC</dt><dd>0951804798001</dd></div>
        <div class="field"><dt>Estado</dt><dd>Activo</dd></div>
        <div class="field"><dt>Régimen</dt><dd>General</dd></div>
        <div class="field"><dt>Tipo</dt><dd>Persona natural</dd></div>
        <div class="field"><dt>Fecha de registro</dt><dd>07/01/2022</dd></div>
        <div class="field"><dt>Jurisdicción</dt><dd>Zona 8 / Guayas / Guayaquil</dd></div>
      </dl>
    </section>

    <section class="card">
      <h2>Actividades económicas registradas</h2>
      <ul class="activities">
        <li v-for="activity in activities" :key="activity.code" :style="activity.main ? 'border: 2px solid var(--accent);' : ''">
          <code>{{ activity.code }}</code><strong v-if="activity.main">{{ activity.label }}</strong><template v-else>{{ activity.label }}</template>{{ activity.note }}
        </li>
      </ul>
    </section>

    <section class="card">
      <h2>Domicilio tributario y contacto</h2>
      <div class="contact-grid">
        <div>
          <div class="field"><dt>Domicilio tributario (SRI)</dt>
            <dd>Barrio Urbanor, Av. 27 NO N.º 11<br/>
            Intersección C. 15A NO, Manzana 130<br/>
            A 1 cuadra de la Escuela Almirante Nelson<br/>
            Tarqui, Guayaquil, Guayas</dd>
          </div>
        </div>
        <div>
          <div class="field"><dt>Atención al público</dt>
            <dd>Ciudadela Álamos Norte<br/>Guayaquil, Guayas</dd>
          </div>
        </div>
        <div>
          <div class="field"><dt>Email</dt><dd>memoscell@gmail.com</dd></div>
        </div>
        <div>
          <div class="field"><dt>Celular</dt><dd>0959196721</dd></div>
        </div>
        <div>
          <div class="field"><dt>Sitio web</dt><dd><a href="https://memos.com.ec" target="_blank" rel="noopener">memos.com.ec</a></dd></div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <p>Información obtenida del Certificado de Registro Único de Contribuyentes emitido por el
    Servicio de Rentas Internas (SRI) del Ecuador. Puede verificar la vigencia de este registro
    directamente en <a href="https://www.sri.gob.ec" target="_blank" rel="noopener">www.sri.gob.ec</a>
    o en la app SRI Móvil.</p>
    <span class="verif-code">Código de verificación del certificado: RCR1789154507267614</span>
  </footer>
</template>

<style>
:root {
  --bg: #f5f5f5;
  --card: #ffffff;
  --ink: #1a1a1a;
  --muted: #6b7280;
  --accent: #111111;
  --accent-soft: #e5e5e5;
  --ok: #15803d;
  --ok-soft: #dcfce7;
  --border: #e5e7eb;
}
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  background: var(--bg);
  color: var(--ink);
  line-height: 1.5;
}
header {
  background: linear-gradient(135deg, #000000, #2b2b2b);
  color: #fff;
  padding: 48px 24px 64px;
  text-align: center;
}
header h1 { margin: 0 0 8px; font-size: 2.2rem; letter-spacing: 0.08em; }
header p { margin: 0; color: #d1d5db; font-size: 1rem; }
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  margin-top: 18px;
  background: var(--ok-soft);
  color: var(--ok);
  font-weight: 600;
  padding: 6px 16px;
  border-radius: 999px;
  font-size: 0.85rem;
}
main {
  max-width: 880px;
  margin: -36px auto 60px;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 28px 30px;
  box-shadow: 0 4px 16px rgba(0,0,0,0.04);
}
.card h2 {
  margin: 0 0 18px;
  font-size: 1.1rem;
  color: var(--accent);
  text-transform: uppercase;
  letter-spacing: 0.04em;
}
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 18px 24px;
}
.field dt {
  font-size: 0.78rem;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 0.03em;
  margin-bottom: 4px;
}
.field dd { margin: 0; font-weight: 600; }
ul.activities { list-style: none; margin: 0; padding: 0; display: flex; flex-direction: column; gap: 10px; }
ul.activities li {
  background: var(--accent-soft);
  border-radius: 10px;
  padding: 12px 16px;
  font-size: 0.95rem;
}
ul.activities code {
  display: inline-block;
  background: #fff;
  border-radius: 6px;
  padding: 1px 6px;
  margin-right: 8px;
  font-size: 0.8rem;
  color: var(--accent);
}
.contact-grid { display: flex; flex-wrap: wrap; gap: 24px; }
.contact-grid div { min-width: 180px; }
footer {
  max-width: 880px;
  margin: 0 auto 60px;
  padding: 0 20px;
  color: var(--muted);
  font-size: 0.82rem;
  text-align: center;
}
footer a { color: var(--accent); }
.verif-code {
  font-family: 'Consolas', monospace;
  background: #fff;
  border: 1px dashed var(--border);
  border-radius: 8px;
  padding: 8px 12px;
  display: inline-block;
  margin-top: 8px;
  font-size: 0.8rem;
}
</style>
