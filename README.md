<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Despacho Jurídico Profesional | Mario José López Villatoro</title>
  <link href="https://fonts.googleapis.com/css2?family=Lobster&family=Playfair+Display:wght@600&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    :root {
      --azul-oscuro: #111827;
      --azul-medio: #1f2937;
      --dorado: #c5a059;
      --gris-fondo: #f3f4f6;
      --blanco: #ffffff;
    }

    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background-color: var(--gris-fondo);
      color: #333;
      overflow-x: hidden;
    }

    /* HEADER RESPONSIVO */
    header {
      background: var(--azul-oscuro);
      color: white;
      padding: 20px 5%;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      border-bottom: 4px solid var(--dorado);
    }

    .logo-container img {
      width: 80px;
      height: auto;
      margin-bottom: 15px;
      border: 2px solid var(--dorado);
      border-radius: 4px;
    }

    .header-text h1 {
      /* CAMBIO A FUENTE LOBSTER */
      font-family: 'Lobster', cursive;
      margin: 0;
      font-size: 1.8em; 
      letter-spacing: 1px;
      /* Lobster se ve mejor sin mayúsculas forzadas, pero puedes dejarlo si prefieres */
      text-transform: none; 
      font-weight: 400;
    }

    .header-text h3 {
  margin: 5px 0 0 0;
  color: var(--dorado); /* Sigue usando el código #c5a059 definido arriba */
  font-weight: 600;
  font-size: 1.10em;
  letter-spacing: 1px;

    }

    /* NAVEGACIÓN */
    nav {
      background: var(--azul-medio);
      display: flex;
      justify-content: center;
      box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1);
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    nav a {
      color: #e5e7eb;
      text-decoration: none;
      padding: 15px 5px;
      font-size: 0.7em;
      font-weight: 600;
      text-transform: uppercase;
      flex: 1;
      text-align: center;
      cursor: pointer;
      border-bottom: 3px solid transparent;
      transition: 0.3s;
    }

    nav a:hover, nav a.active {
      color: var(--dorado);
      border-bottom: 3px solid var(--dorado);
      background: rgba(255,255,255,0.05);
    }

    /* CONTENEDOR PRINCIPAL */
    .main-wrapper {
      display: grid;
      grid-template-columns: 1fr;
      max-width: 1300px;
      margin: 20px auto;
      gap: 20px;
      padding: 0 15px;
    }

    .view-content {
      background: var(--blanco);
      padding: 25px;
      border-radius: 8px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.05);
      text-align: center;
    }

    .img-presentacion {
      width: 80%;
      max-width: 300px;
      border-radius: 8px;
      margin: 20px auto;
      display: block;
    }

    /* SIDEBAR - OCULTO POR DEFECTO */
    .sidebar {
      background: var(--blanco);
      padding: 25px;
      border-radius: 8px;
      border-top: 5px solid var(--azul-oscuro);
      text-align: center;
      display: none; 
    }

    .btn-contact {
      background: #25d366;
      color: white;
      text-decoration: none;
      display: block;
      padding: 12px;
      text-align: center;
      border-radius: 5px;
      font-weight: 600;
      margin-top: 20px;
    }

    /* TRÁMITES */
    .grid-tramites {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      margin-top: 20px;
    }

    .card-btn {
      background: var(--azul-oscuro);
      color: white;
      padding: 15px 5px;
      border: none;
      border-bottom: 3px solid var(--dorado);
      border-radius: 4px;
      font-family: 'Poppins', sans-serif;
      font-weight: 600;
      font-size: 0.8em;
      cursor: pointer;
    }

    .info-box {
      background: #f9fafb;
      padding: 20px;
      border-left: 5px solid var(--azul-oscuro);
      margin-top: 20px;
      display: none;
      text-align: left;
      animation: fadeIn 0.5s;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* AJUSTES PC */
    @media (min-width: 900px) {
      header { flex-direction: row; text-align: left; padding: 25px 8%; }
      .logo-container img { margin-bottom: 0; margin-right: 25px; width: 90px; }
      .header-text h1 { font-size: 2.5em; }
      nav a { flex: none; padding: 15px 25px; font-size: 0.85em; }
      .main-wrapper.has-sidebar { grid-template-columns: 3fr 1fr; }
      .view-content { text-align: left; padding: 40px; }
      .img-presentacion { margin: 20px 0; }
      .sidebar { text-align: left; }
      .grid-tramites { grid-template-columns: repeat(3, 1fr); }
    }
  </style>
</head>
<body>

<header>
  <div class="logo-container">
    <img src="img.html" alt="Logo">
  </div>
  <div class="header-text">
    <h1>Despacho Jurídico Profesional</h1>
    <h3>Lic. Mario José López Villatoro</h3>
  </div>
</header>

<nav id="mainNav">
  <a onclick="showView('inicio', event)" class="active">Inicio</a>
  <a onclick="showView('tramites', event)">Trámites</a>
  <a onclick="showView('contacto', event)">Contacto</a>
  <a onclick="showView('ubicacion', event)">Ubicación</a>
</nav>

<div class="main-wrapper" id="mainWrapper">
  <main class="view-content" id="dynamicView">
    <section id="content-inicio">
      <h2>Bienvenidos:Despacho Jurídico Profecional</h2>
      <p>Brindamos asesoría legal integral con los más altos estándares de ética y profesionalismo en Santa Rosa de Lima.</p>
      <img src="img.html" class="img-presentacion" alt="Oficina">
    </section>
  </main>

  <aside class="sidebar" id="sidebarContact">
    <h3>Contacto📱</h3>
    <p><strong>📱 WhatsApp:</strong><br>+503 7986-2883</p>
    <a href="https://wa.me/50379862883" class="btn-contact">Chat Directo WhatsApp</a>
  </aside>
</div>

<script>
  const tramitesData = {
    divorcio: "<h3>Divorcios</h3><ul><li>Mutuo Consentimiento</li><li>Separaciones por más de un año</li><li>Vida Intolerable</li></ul>",
    escrituras: "<h3>Escrituras</h3><ul><li>Poderes</li><li>Compra venta</li><li>Matrimonios</li><li>Testamentos</li></ul>",
    laboral: "<h3>Derecho Laboral</h3><ul><li>Despidos e Indemnizaciones</li><li>Cálculo de Aguinaldos</li><li>Conflictos Patronales</li></ul>",
    familia: "<h3>Derecho Familiar</h3><ul><li>Cuotas Alimenticias</li><li>Cuidado Personal</li><li>Reconocimiento de hijos</li></ul>",
    contratos: "<h3>Contratos</h3><ul><li>Arrendamientos</li><li>Promesas de Venta</li><li>Mutuos Hipotecarios</li><li>Letras de Cambio</li></ul>",
    notarial: "<h3>Servicios Notariales</h3><ul><li>Actas Notariales</li><li>Autenticaciones</li><li>Certificaciones</li></ul>"
  };

  function showView(view, event) {
    const container = document.getElementById('dynamicView');
    const sidebar = document.getElementById('sidebarContact');
    const wrapper = document.getElementById('mainWrapper');
    
    document.querySelectorAll('#mainNav a').forEach(a => a.classList.remove('active'));
    if(event) event.target.classList.add('active');

    if (view === 'contacto') {
      sidebar.style.display = 'block';
      wrapper.classList.add('has-sidebar');
    } else {
      sidebar.style.display = 'none';
      wrapper.classList.remove('has-sidebar');
    }

    if (view === 'inicio') {
      container.innerHTML = `
        <h2>Bienvenidos</h2>
        <p>Asesoría legal confiable y eficiente. Nuestra experiencia garantiza la seguridad jurídica que usted necesita.</p>
        <img src="Mariolopez.jpeg" class="img-presentacion" alt="Oficina">
      `;
    } 
    else if (view === 'tramites') {
      container.innerHTML = `
        <h2>Consulta de Servicios Legales</h2>
        <p>Seleccione un área para ver detalles:</p>
        <div class="grid-tramites">
          <button class="card-btn" onclick="verDetalle('divorcio')">Divorcios</button>
          <button class="card-btn" onclick="verDetalle('escrituras')">Escrituras</button>
          <button class="card-btn" onclick="verDetalle('laboral')">Derecho Laboral</button>
          <button class="card-btn" onclick="verDetalle('familia')">Derecho Familiar</button>
          <button class="card-btn" onclick="verDetalle('contratos')">Contratos</button>
          <button class="card-btn" onclick="verDetalle('notarial')">Notariado</button>
        </div>
        <div id="detalleTramite" class="info-box"></div>
      `;
    }
    else if (view === 'contacto') {
      container.innerHTML = `
        <h2>Información de Contacto</h2>
<p>Estamos para servirle en los siguientes canales:</p>

<div style="display:flex; flex-direction:column; gap:12px; margin-top:15px;">

  <!-- TELÉFONO -->
  <a href="tel:+50326642008" style="text-decoration:none;">
    <button style="
      width:100%;
      background:#0f172a;
      color:white;
      padding:14px;
      border:none;
      border-radius:10px;
      font-size:16px;
      font-weight:600;
      cursor:pointer;
    ">
      ☎ Llamar al Teléfono Fijo
    </button>
  </a>

  <!-- WHATSAPP -->
  <a href="https://wa.me/50379862883" target="_blank" style="text-decoration:none;">
    <button style="
      width:100%;
      background:#25d366;
      color:white;
      padding:14px;
      border:none;
      border-radius:10px;
      font-size:16px;
      font-weight:600;
      cursor:pointer;
    ">
      📱 Enviar WhatsApp
    </button>
  </a>

  <!-- EMAIL -->
  <a href="mailto:Villatoro1997lopez@gmail.com" style="text-decoration:none;">
    <button style="
      width:100%;
      background:#1e293b;
      color:white;
      padding:14px;
      border:none;
      border-radius:10px;
      font-size:16px;
      font-weight:600;
      cursor:pointer;
    ">
      📧 Enviar Correo
    </button>
  </a>

</div>
      `;
    }
    else if (view === 'ubicacion') {
      container.innerHTML = `
        <h2>Nuestra Ubicación</h2>
        <p>📍 2ª Av. Sur, Barrio El Convento, Santa Rosa de Lima, La Unión, El Salvador, C.A.</p>
        <div style="background:#eee; height:250px; display:flex; align-items:center; justify-content:center; border-radius:8px;">
          <a class="btn-contact" style="background:var(--azul-oscuro); padding:15px 25px;" href="https://www.google.com/maps/place/OFICINA+JURIDICA+LIC.+MARIO+JOSE+LOPEZ+VILLATORO/@13.6243633,-87.8943883,746m/data=!3m2!1e3!4b1!4m6!3m5!1s0x8f65358233f3b8bb:0xa752525964c75680!8m2!3d13.6243581!4d-87.8918134!16s%2Fg%2F11qnvp63f_?entry=ttu&g_ep=EgoyMDI2MDUwMi4wIKXMDSoASAFQAw%3D%3D" target="_blank">Ver en Google Maps</a>
        </div>
      `;
    }
    window.scrollTo(0,0);
  }

  function verDetalle(tipo) {
    const detalleDiv = document.getElementById('detalleTramite');
    detalleDiv.innerHTML = tramitesData[tipo] + '<a href="https://wa.me/50379862883" class="btn-contact" style="display:inline-block; width:200px;">Consultar ahora</a>';
    detalleDiv.style.display = 'block';
    detalleDiv.scrollIntoView({behavior: 'smooth', block: 'center'});
  }
</script>

</body>
</html>
