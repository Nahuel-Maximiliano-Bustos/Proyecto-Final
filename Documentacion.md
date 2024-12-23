# Documentación del Sitio Web

## Descripción General

Este documento proporciona una visión general del sitio web, describiendo su estructura, diseño y características principales. El sitio está diseñado con un enfoque en la estética y funcionalidad, utilizando HTML y CSS para construir una experiencia de usuario fluida y responsiva.

## Estructura del Proyecto

### 1. **HTML**

El sitio web está compuesto por varias secciones principales:

- **Header:** Contiene la barra de navegación y el logotipo.
- **Footer:** Incluye los enlaces a redes sociales y otra información de contacto.
- **Secciones de Contenido:** Incluye las secciones destacadas, planes y membresías, testimonios, y el blog.
- **Ventanas Emergentes:** Utilizadas para mostrar formularios y mensajes de confirmación.
- **Barra de Carga:** Indica el progreso de ciertas acciones o cargas en el sitio.

### 2. **CSS**

Los estilos están organizados en varias categorías para facilitar la administración:

- **Estilos Generales:** Configura el estilo básico del texto y los botones.
- **Header y Navegación:** Estilos para el encabezado y el menú de navegación, con soporte para la navegación en dispositivos móviles.
- **Footer:** Estilos para el pie de página y los íconos sociales.
- **Secciones:** Estilos para las secciones destacadas, planes y membresías, y testimonios.
- **Ventanas Emergentes:** Diseño y comportamiento de las ventanas emergentes.
- **Barra de Carga:** Estilos para la barra de carga con animaciones.
- **Blog:** Estilos para la sección del blog, incluyendo tarjetas para los artículos.

## Detalle de Componentes

### Header

El **header** incluye el logotipo y un menú de navegación. El menú se convierte en un menú desplegable en pantallas pequeñas. La visibilidad del menú se controla mediante un checkbox oculto (`#menu-toggle`) y la clase `menu-icon`.

.header {
    background-color: #000000;
    color: #FFFFFF;
    padding: 10px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    z-index: 1000;
    box-sizing: border-box;
}

.header .logo img {
    height: 50px;
    max-width: 100%;
}

.menu-icon {
    display: none;
    font-size: 24px;
    cursor: pointer;
    color: #FFFFFF;
}

.nav-menu {
    display: flex;
    justify-content: flex-end;
    gap: 15px;
}

.menu {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    gap: 15px;
}

.menu li a {
    color: #FFFFFF;
    text-decoration: none;
    font-weight: bold;
}

.menu li a:hover {
    color: #FFC107;
}

#menu-toggle {
    display: none;
}

#menu-toggle:checked + .menu-icon + .nav-menu {
    display: flex;
    flex-direction: column;
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
    background-color: #000000;
    padding: 10px 0;
    box-sizing: border-box;
    z-index: 1000;
}

@media (max-width: 768px) {
    .header {
        padding: 10px;
        flex-direction: row;
    }

    .nav-menu {
        display: none;
        width: 100%;
    }

    .menu-icon {
        display: block;
        margin-left: auto;
    }

    #menu-toggle:checked + .menu-icon + .nav-menu {
        display: flex;
    }

    .menu {
        display: flex;
        flex-direction: column;
        width: 100%;
        gap: 10px;
        padding: 10px 0;
        background-color: #000000;
    }

    .menu li {
        text-align: center;
        margin: 0;
    }
}

Footer
El footer presenta un fondo oscuro con texto blanco, y está centrado para mostrar los enlaces a redes sociales.

.footer {
    background-color: #000000;
    color: #FFFFFF;
    padding: 20px;
    text-align: center;
}

.social-icons a {
    margin: 0 10px;
    display: inline-block;
}

.social-icons img {
    height: 50px;
    width: auto;
}

Secciones
Sección Destacada
La sección destacada usa un video de fondo y texto centralizado sobre un fondo semitransparente.

.section-highlight {
    position: relative;
    height: 100vh;
    overflow: hidden;
}

.section-highlight .video-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: -1;
}

.section-highlight video {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
    transform: translate(-50%, -50%);
}

.section-highlight .welcome-text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: rgba(60, 62, 65, 0.5);
    padding: 20px;
    color: #FFFFFF;
    text-align: center;
}

Planes y Membresías
Los planes y membresías están organizados en un diseño flexible que permite la adaptación a diferentes tamaños de pantalla.

.section-light {
    background-color: #E9ECEF;
    padding: 20px;
    text-align: center;
}

.membresias {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
}

.membresia {
    background-color: #FFFFFF;
    border: 1px solid #C0C0C0;
    padding: 20px;
    margin: 10px;
    text-align: center;
    width: 100%;
    max-width: 300px;
    box-sizing: border-box;
    transition: transform 0.3s ease;
}

.membresia:hover {
    transform: scale(1.05);
}

.membresia img {
    height: 100px;
    margin-bottom: 10px;
}

.membresia h3 {
    margin: 10px 0;
}

.membresia p {
    font-size: 0.9em;
}


Testimonios
La sección de testimonios usa un carrusel para mostrar diferentes opiniones. Los estilos incluyen un diseño responsive y animaciones para la transición entre testimonios.

.testimonios {
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 1000px;
    margin: 0 auto;
    text-align: center;
}

.testimonios .carousel {
    display: flex;
    transition: transform 0.5s ease-in-out;
    width: 100%;
}

.testimonios .carousel-slide {
    flex: 1 0 100%;
    display: none;
}

#carousel1:checked ~ .carousel .carousel-slide:nth-of-type(1),
#carousel2:checked ~ .carousel .carousel-slide:nth-of-type(2),
#carousel3:checked ~ .carousel .carousel-slide:nth-of-type(3),
#carousel4:checked ~ .carousel .carousel-slide:nth-of-type(4),
#carousel5:checked ~ .carousel .carousel-slide:nth-of-type(5),
#carousel6:checked ~ .carousel .carousel-slide:nth-of-type(6) {
    display: flex; 
}

.testimonios .testimonio {
    background-color: #FFFFFF;
    border: 1px solid #C0C0C0;
    padding: 20px;
    width: 100%;
    max-width: 600px;
    box-sizing: border-box;
    transition: transform 0.3s ease;
    position: relative;
    flex-direction: row;
    margin: 0 auto; 
    margin-bottom: 40px;
}

.testimonios .testimonio:hover {
    transform: scale(1.02);
}

.testimonios .testimonio img {
    height: 100px;
    margin-right: 20px;
    border-radius: 50%;
    flex-shrink: 0;
}

.testimonios .testimonio .testimonio-texto {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.testimonios .testimonio h3 {
    margin: 0;
    font-size: 1.2em;
    color: #343A40;
}

.testimonios .testimonio p {
    margin: 5px 0;
    font-size: 1em;
    color: #343A40;
}

.testimonios .testimonio .rating {
    position: static;
    margin-top: 10px;
    text-align: right;
}

.rating .stars {
    color: #FFC107;
    font-size: 1.2em;
}

.rating .percentage {
    font-size: 0.8em;
    color: #343A40;
}

Blog
La sección del blog presenta artículos en tarjetas que incluyen una imagen a la derecha y el texto a la izquierda. Los artículos se pueden expandir o contraer con botones.

<section id="blog" class="section-light">
    <div class="container">
        <h2>Blog</h2>
        <div class="blog-articles">
            <!-- Article 1 -->
            <div class="blog-card">
                <div class="blog-image">
                    <img src="ruta/a/imagen1.jpg" alt="Artículo 1">
                </div>
                <div class="blog-content">
                    <h3>Título del Artículo 1</h3>
                    <hr>
                    <p class="blog-text">
                        Contenido del artículo 1...
                    </p>
                    <button class="toggle-content">Ver más</button>
                </div>
            </div>
            <!-- Libertad de añadir nuevos articulos -->
        </div>
    </div>
</section>

.blog-card {
    display: flex;
    background-color: #FFFFFF;
    border: 1px solid #C0C0C0;
    margin-bottom: 20px;
    padding: 15px;
    border-radius: 8px;
    transition: box-shadow 0.3s ease;
}

.blog-card:hover {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.blog-image img {
    width: 150px;
    height: auto;
    border-radius: 8px;
}

.blog-content {
    margin-left: 15px;
    flex: 1;
}

.blog-content h3 {
    margin: 0;
}

.blog-content hr {
    border: none;
    height: 1px;
    background-color: #C0C0C0;
    margin: 10px 0;
}

.blog-content .blog-text {
    display: none;
}

.blog-content .toggle-content {
    background-color: #FFC107;
    color: #FFFFFF;
    border: none;
    padding: 10px;
    cursor: pointer;
    border-radius: 4px;
}

.blog-content .toggle-content:hover {
    background-color: #FFD54F;
}

@media (max-width: 768px) {
    .blog-card {
        flex-direction: column;
    }

    .blog-image img {
        width: 100%;
    }

    .blog-content {
        margin-left: 0;
    }
}


Ventanas Emergentes
Las ventanas emergentes se utilizan para formularios de membresía y mensajes de confirmación. Se implementan sin JavaScript mediante el uso de checkboxes y etiquetas.

<!-- Ventana Emergente para Membresía -->
<input type="checkbox" id="modal1" class="modal-toggle">
<label for="modal1" class="modal-overlay"></label>
<div class="modal-content">
    <h2>Suscripción a Membresía</h2>
    <form action="#">
        <!-- Formulario de Membresía -->
        <label for="membership-type">Tipo de Membresía:</label>
        <select id="membership-type" name="membership-type">
            <option value="basic">Básica</option>
            <option value="premium">Premium</option>
        </select>
        <button type="submit">Suscribirse</button>
    </form>
    <label for="modal1" class="modal-close">X</label>
</div>

.modal-toggle {
    display: none;
}

.modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s ease, visibility 0.3s ease;
}

.modal-toggle:checked + .modal-overlay {
    opacity: 1;
    visibility: visible;
}

.modal-content {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #FFFFFF;
    padding: 20px;
    border-radius: 8px;
    width: 80%;
    max-width: 500px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    z-index: 1001;
    transition: transform 0.3s ease;
}

.modal-close {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 24px;
    cursor: pointer;
}

Conclusión

Esta documentación detalla la estructura y los estilos del sitio web. Cada componente está diseñado para ser adaptable y proporcionar una experiencia de usuario intuitiva y atractiva. La implementación de ventanas emergentes sin JavaScript y el uso de un diseño responsive aseguran que el sitio funcione bien en una variedad de dispositivos.

Para cualquier ajuste o pregunta adicional, no dudes en contactar.