<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Moonshine - Gestión de Inventario</title>

  <link rel="stylesheet" href="style.css">

  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>

<body>

  <aside class="sidebar">

    <div class="logo-container">
      <img src="img.jpg/imgLogoMoonshine.jpeg" alt="">
      <h2>Moonshine</h2>
    </div>

    <nav>

      <a href="#" onclick="mostrarSeccion('inicio')">
        <i class="fa-solid fa-house"></i>
        Inicio
      </a>

      <a href="#" onclick="mostrarSeccion('inventario')">
        <i class="fa-solid fa-boxes-stacked"></i>
        Inventario
      </a>

      <a href="#" onclick="mostrarSeccion('estadisticas')">
        <i class="fa-solid fa-chart-column"></i>
        Estadísticas
      </a>

      <a href="#" onclick="mostrarSeccion('login')">
        <i class="fa-solid fa-user"></i>
        Login
      </a>

    </nav>

  </aside>

  <main class="main">

    <header class="topbar">

      <div>
        <h1>Sistema de Gestión de Almacenamiento</h1>
        <p>Control inteligente de inventario</p>
      </div>

      <div class="admin">
        <i class="fa-solid fa-user-shield"></i>
        <span>Administrador</span>
      </div>

    </header>

    <section class="hero section active" id="inicio">

      <div class="hero-text">

        <h2>
          CONTROL TOTAL DE INVENTARIO
        </h2>

        <p>
          Gestiona productos, entradas, salidas y estadísticas en tiempo real.
        </p>

        <button onclick="mostrarSeccion('inventario')">
          Explorar Inventario
        </button>

      </div>

      <div class="hero-image">
        <img src="img.jpg/imgLogoMoonshine.jpeg" alt="">
      </div>

    </section>

    <section class="login section" id="login">

      <div class="login-box">

        <h2>Iniciar Sesión</h2>

        <input type="text" id="user" placeholder="Usuario">

        <input type="password" id="password" placeholder="Contraseña">

        <button onclick="Login()">
          Entrar
        </button>

      </div>

    </section>

    <section class="inventario section" id="inventario">

      <div class="cards">

        <div class="card">
          <i class="fa-solid fa-box"></i>
          <h3 id="totalProductos">0</h3>
          <p>Productos</p>
        </div>

        <div class="card">
          <i class="fa-solid fa-warehouse"></i>
          <h3 id="stockTotal">0</h3>
          <p>Stock Total</p>
        </div>

        <div class="card">
          <i class="fa-solid fa-dollar-sign"></i>
          <h3 id="valorInventario">$0</h3>
          <p>Valor Inventario</p>
        </div>

      </div>

      <div class="tabla-container">

        <table>

          <thead>

            <tr>
              <th>Imagen</th>
              <th>Producto</th>
              <th>Cantidad</th>
              <th>Precio</th>
              <th>Estado</th>
              <th>Fecha</th>
              <th>Acciones</th>
            </tr>

          </thead>

          <tbody id="tablaProductos">

            <tr>

              <td>
                <img src="img.jpg/imgcrema.avif" class="img-producto">
              </td>

              <td>Crema Personal</td>

              <td class="cantidad">50</td>

              <td class="precio">10000</td>

              <td>
                <span class="estado entrada">Disponible</span>
              </td>

              <td class="fecha"></td>

              <td>

                <button class="editar" onclick="editarFila(this)">
                  Editar
                </button>

                <button class="eliminar" onclick="eliminarFila(this)">
                  Eliminar
                </button>

              </td>

            </tr>

            <tr>

              <td>
                <img src="img.jpg/imgCoco.jpg" class="img-producto">
              </td>

              <td>Aceite de Coco</td>

              <td class="cantidad">10</td>

              <td class="precio">20000</td>

              <td>
                <span class="estado salida">Pocas unidades</span>
              </td>

              <td class="fecha"></td>

              <td>

                <button class="editar" onclick="editarFila(this)">
                  Editar
                </button>

                <button class="eliminar" onclick="eliminarFila(this)">
                  Eliminar
                </button>

              </td>

            </tr>

          </tbody>

        </table>

      </div>

      <div class="agregar-container">

        <input type="text" id="nombreProducto" placeholder="Nombre">

        <input type="number" id="cantidadProducto" placeholder="Cantidad">

        <input type="number" id="precioProducto" placeholder="Precio">

        <input type="file" id="imagenInput">

        <button onclick="agregarProducto()">
          Agregar Producto
        </button>

      </div>

    </section>

    <section class="estadisticas section" id="estadisticas">

      <div class="graficas">

        <div class="grafica-card">
          <canvas id="graficaStock"></canvas>
        </div>

        <div class="grafica-card">
          <canvas id="graficaValor"></canvas>
        </div>

      </div>

    </section>

  </main>

  <script src="script.js"></script>

</body>

</html>
