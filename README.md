<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>La Perrera - Hot Dogs Muy Perros</title>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=Archivo+Black&family=Inter:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
:root {
    --amarillo: #f5b81f;
    --amarillo-hover: #e0a810;
    --rojo: #e8451c;
    --rojo-hover: #cc3a15;
    --negro: #0d0d0d;
    --negro-2: #1a1a1a;
    --negro-3: #252525;
    --texto: #ffffff;
    --texto-gris: #999;
}
* { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
html { scroll-behavior: smooth; }
body {
    background: var(--negro);
    color: var(--texto);
    font-family: 'Inter', sans-serif;
    overflow-x: hidden;
    padding-bottom: 100px;
}

/* ============ HEADER ============ */
.topbar {
    background: var(--amarillo);
    padding: 12px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 1000;
}
.logo {
    font-family: 'Archivo Black', sans-serif;
    font-size: 2rem;
    color: var(--negro);
    letter-spacing: -1px;
    line-height: 1;
}
.nav-links { display: none; gap: 28px; }
.nav-links a {
    font-family: 'Anton', sans-serif;
    color: var(--negro);
    text-decoration: none;
    font-size: 1.1rem;
    letter-spacing: 1px;
}
.btn-gift {
    background: var(--rojo);
    color: #fff;
    padding: 12px 22px;
    font-family: 'Anton', sans-serif;
    font-size: 1rem;
    letter-spacing: 1px;
    border: none;
    cursor: pointer;
    text-decoration: none;
    border-radius: 4px;
}

/* MENÚ MÓVIL */
.menu-btn {
    background: none;
    border: none;
    font-size: 1.8rem;
    color: var(--negro);
    cursor: pointer;
}
.mobile-menu {
    display: none;
    background: var(--amarillo);
    border-top: 2px solid var(--negro);
    padding: 16px 24px;
    flex-direction: column;
    gap: 12px;
    position: sticky;
    top: 60px;
    z-index: 999;
}
.mobile-menu.open { display: flex; }
.mobile-menu a {
    font-family: 'Anton', sans-serif;
    color: var(--negro);
    text-decoration: none;
    font-size: 1.3rem;
    letter-spacing: 1px;
}

/* ============ HERO ============ */
.hero {
    background: linear-gradient(135deg, #0d0d0d 0%, #1a1a1a 50%, #2a1a0a 100%);
    padding: 60px 24px 80px;
    position: relative;
    overflow: hidden;
    min-height: 420px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 80% 50%, rgba(232,69,28,0.15), transparent 60%);
}
.hero-eyebrow {
    font-family: 'Anton', sans-serif;
    color: var(--rojo);
    font-size: 1rem;
    letter-spacing: 4px;
    margin-bottom: 16px;
    position: relative;
}
.hero-title {
    font-family: 'Anton', sans-serif;
    color: var(--amarillo);
    font-size: 3rem;
    line-height: 0.95;
    letter-spacing: -1px;
    margin-bottom: 24px;
    position: relative;
}
.hero-badge {
    display: inline-block;
    background: var(--rojo);
    color: #fff;
    padding: 14px 28px;
    font-family: 'Anton', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 2px;
    text-decoration: none;
    align-self: flex-start;
    border-radius: 4px;
    position: relative;
}

/* ============ MARQUEE ============ */
.marquee {
    background: var(--rojo);
    padding: 16px 0;
    overflow: hidden;
    white-space: nowrap;
}
.marquee-inner {
    display: inline-block;
    animation: scroll 25s linear infinite;
    font-family: 'Anton', sans-serif;
    font-size: 2rem;
    color: var(--negro);
    letter-spacing: 2px;
}
.marquee-inner span { margin: 0 24px; color: var(--amarillo); }
@keyframes scroll {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
}

/* ============ CATEGORÍAS STICKY ============ */
.cat-nav {
    background: var(--amarillo);
    position: sticky;
    top: 60px;
    z-index: 900;
    border-top: 3px solid var(--negro);
    border-bottom: 3px solid var(--negro);
    padding: 12px 0;
    overflow-x: auto;
    scrollbar-width: none;
}
.cat-nav::-webkit-scrollbar { display: none; }
.cat-nav-inner {
    display: flex;
    gap: 8px;
    padding: 0 24px;
    white-space: nowrap;
}
.cat-pill {
    background: transparent;
    border: 2px solid var(--negro);
    color: var(--negro);
    padding: 8px 20px;
    font-family: 'Anton', sans-serif;
    font-size: 0.95rem;
    letter-spacing: 1px;
    cursor: pointer;
    text-decoration: none;
    border-radius: 50px;
    transition: all 0.2s;
}
.cat-pill.active {
    background: var(--negro);
    color: var(--amarillo);
}

/* ============ MENÚ ============ */
.menu-wrap { padding: 0 0 40px; }
.cat-section { padding: 32px 24px 8px; }
.cat-title {
    font-family: 'Anton', sans-serif;
    font-size: 1.8rem;
    color: var(--amarillo);
    letter-spacing: 2px;
    margin-bottom: 16px;
    padding-bottom: 8px;
    border-bottom: 3px solid var(--rojo);
    display: inline-block;
}
.producto {
    background: var(--negro-2);
    border: 1px solid var(--negro-3);
    border-left: 4px solid var(--amarillo);
    padding: 18px;
    margin-bottom: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    border-radius: 8px;
    transition: all 0.2s;
}
.producto:active { transform: scale(0.99); border-left-color: var(--rojo); }
.producto-info { flex: 1; min-width: 0; }
.producto-info h3 {
    font-family: 'Anton', sans-serif;
    font-size: 1.15rem;
    letter-spacing: 1px;
    color: #fff;
    margin-bottom: 4px;
}
.producto-info p {
    font-size: 0.82rem;
    color: var(--texto-gris);
    line-height: 1.4;
    margin-bottom: 8px;
}
.producto-precio {
    font-family: 'Anton', sans-serif;
    font-size: 1.3rem;
    color: var(--amarillo);
}
.btn-add {
    background: var(--rojo);
    color: #fff;
    border: none;
    width: 44px;
    height: 44px;
    border-radius: 50%;
    font-size: 1.6rem;
    font-weight: 900;
    cursor: pointer;
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: inherit;
}
.btn-add:active { transform: scale(0.85); }

/* ============ CARRITO ============ */
.cart-overlay {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.75);
    z-index: 2000;
    opacity: 0; pointer-events: none;
    transition: opacity 0.3s;
}
.cart-overlay.open { opacity: 1; pointer-events: auto; }
.cart-panel {
    position: fixed;
    bottom: 0; left: 0; right: 0;
    background: var(--negro-2);
    border-top: 4px solid var(--amarillo);
    border-radius: 20px 20px 0 0;
    max-height: 92vh;
    z-index: 2001;
    transform: translateY(100%);
    transition: transform 0.35s cubic-bezier(0.32,0.72,0,1);
    display: flex; flex-direction: column;
}
.cart-panel.open { transform: translateY(0); }
.cart-head {
    padding: 20px;
    border-bottom: 1px solid var(--negro-3);
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.cart-head h2 {
    font-family: 'Anton', sans-serif;
    font-size: 1.4rem;
    letter-spacing: 1px;
    color: var(--amarillo);
}
.close-btn {
    background: none; border: none; color: #fff;
    font-size: 1.6rem; cursor: pointer;
    width: 36px; height: 36px;
}
.cart-body { padding: 20px; overflow-y: auto; flex: 1; }
.cart-empty { text-align: center; color: var(--texto-gris); padding: 40px 0; font-family: 'Anton', sans-serif; letter-spacing: 1px; }
.cart-item {
    display: flex; justify-content: space-between; align-items: center;
    padding: 12px 0; border-bottom: 1px solid var(--negro-3);
}
.cart-item h4 { font-size: 0.95rem; margin-bottom: 2px; font-weight: 700; }
.cart-item small { color: var(--texto-gris); font-size: 0.8rem; }
.qty-group { display: flex; align-items: center; gap: 10px; }
.qty-btn {
    background: var(--negro-3); border: none; color: #fff;
    width: 32px; height: 32px; border-radius: 8px;
    font-size: 1rem; cursor: pointer;
    display: flex; align-items: center; justify-content: center;
}
.qty-btn:active { background: var(--amarillo); color: var(--negro); }
.qty-num { font-weight: 800; min-width: 22px; text-align: center; }
.cart-item-price { font-family: 'Anton', sans-serif; color: var(--amarillo); min-width: 60px; text-align: right; }

.cart-foot {
    padding: 20px; border-top: 1px solid var(--negro-3);
    background: var(--negro-2);
}
.total-row {
    display: flex; justify-content: space-between; align-items: center;
    font-family: 'Anton', sans-serif; font-size: 1.6rem;
    margin-bottom: 16px; letter-spacing: 1px;
}
.total-row span:last-child { color: var(--amarillo); }
.form-group { margin-bottom: 10px; }
.form-group input, .form-group textarea {
    width: 100%; background: var(--negro-3);
    border: 1px solid #333; color: #fff;
    padding: 13px 16px; border-radius: 8px;
    font-size: 0.95rem; font-family: inherit; outline: none;
}
.form-group input:focus, .form-group textarea:focus { border-color: var(--amarillo); }
.form-group input::placeholder, .form-group textarea::placeholder { color: #666; }
.btn-submit {
    width: 100%; background: var(--rojo); color: #fff;
    border: none; padding: 18px; border-radius: 8px;
    font-family: 'Anton', sans-serif; font-size: 1.15rem;
    letter-spacing: 2px; cursor: pointer;
}
.btn-submit:active { background: var(--rojo-hover); }

/* ============ FLOATING BAR ============ */
.float-bar {
    position: fixed; bottom: 0; left: 0; right: 0;
    background: var(--negro-2); border-top: 3px solid var(--amarillo);
    padding: 12px 20px; display: flex; justify-content: space-between;
    align-items: center; z-index: 800;
    transform: translateY(100%); transition: transform 0.3s;
}
.float-bar.visible { transform: translateY(0); }
.float-info small { color: var(--texto-gris); font-size: 0.75rem; display: block; }
.float-info strong { font-family: 'Anton', sans-serif; color: var(--amarillo); font-size: 1.4rem; letter-spacing: 1px; }
.float-bar button {
    background: var(--rojo); color: #fff; border: none;
    padding: 12px 24px; border-radius: 6px;
    font-family: 'Anton', sans-serif; font-size: 1rem;
    letter-spacing: 1px; cursor: pointer;
}

/* ============ FOOTER ============ */
.footer {
    background: #000;
    padding: 40px 24px 30px;
    border-top: 4px solid var(--rojo);
    margin-top: 40px;
}
.footer h3 {
    font-family: 'Anton', sans-serif;
    color: var(--rojo);
    font-size: 1.3rem;
    letter-spacing: 2px;
    margin-bottom: 10px;
    margin-top: 20px;
}
.footer p, .footer a {
    color: var(--amarillo);
    text-decoration: none;
    font-size: 0.9rem;
    display: block;
    margin-bottom: 4px;
}
.footer-logo {
    font-family: 'Archivo Black', sans-serif;
    font-size: 2rem;
    color: var(--amarillo);
    margin-bottom: 8px;
}
.footer-copy {
    margin-top: 30px; padding-top: 20px;
    border-top: 1px solid #222;
    font-size: 0.75rem; color: #666; text-align: center;
}

/* ============ TOAST ============ */
.toast {
    position: fixed; top: 90px; left: 50%;
    transform: translateX(-50%) translateY(-20px);
    background: var(--amarillo); color: var(--negro);
    padding: 12px 24px; border-radius: 50px;
    font-family: 'Anton', sans-serif; letter-spacing: 1px;
    opacity: 0; pointer-events: none;
    transition: all 0.3s; z-index: 3000;
}
.toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }

/* ============ RESPONSIVE ============ */
@media (min-width: 768px) {
    .nav-links { display: flex; }
    .menu-btn { display: none; }
    .hero-title { font-size: 5rem; }
    .cat-nav { top: 68px; }
}
</style>
</head>
<body>

<!-- HEADER -->
<div class="topbar">
    <div class="logo">la perrera</div>
    <nav class="nav-links">
        <a href="#menu">MENU</a>
        <a href="#contacto">CONTACTO</a>
        <a href="#nosotros">NOSOTROS</a>
    </nav>
    <a href="#menu" class="btn-gift">PEDIR AHORA</a>
    <button class="menu-btn" onclick="toggleMobile()">☰</button>
</div>
<div class="mobile-menu" id="mobileMenu">
    <a href="#menu" onclick="toggleMobile()">MENU</a>
    <a href="#contacto" onclick="toggleMobile()">CONTACTO</a>
    <a href="#nosotros" onclick="toggleMobile()">NOSOTROS</a>
</div>

<!-- HERO -->
<section class="hero">
    <div class="hero-eyebrow">PERROS ❉ CALIENTES ❉ Y MAS</div>
    <h1 class="hero-title">HOT DOGS<br>MUY PERROS</h1>
    <a href="#menu" class="hero-badge">ORDENAR EN LÍNEA</a>
</section>

<!-- MARQUEE -->
<div class="marquee">
    <div class="marquee-inner">
        <span>PERROS</span>❉<span>CALIENTES</span>❉<span>SABROSOS</span>❉<span>PERROS</span>❉<span>CALIENTES</span>❉<span>SABROSOS</span>❉
        <span>PERROS</span>❉<span>CALIENTES</span>❉<span>SABROSOS</span>❉<span>PERROS</span>❉<span>CALIENTES</span>❉<span>SABROSOS</span>❉
    </div>
</div>

<!-- CATEGORÍAS -->
<nav class="cat-nav">
    <div class="cat-nav-inner" id="catNav"></div>
</nav>

<!-- MENÚ -->
<div class="menu-wrap" id="menu"></div>

<!-- CARRITO -->
<div class="cart-overlay" id="cartOverlay" onclick="toggleCart()"></div>
<div class="cart-panel" id="cartPanel">
    <div class="cart-head">
        <h2>TU PEDIDO</h2>
        <button class="close-btn" onclick="toggleCart()">✕</button>
    </div>
    <div class="cart-body">
        <div id="cartItems"></div>
        <div class="cart-foot">
            <div class="total-row"><span>TOTAL</span><span id="cartTotal">$0</span></div>
            <div class="form-group"><input type="text" id="nombre" placeholder="Nombre completo *"></div>
            <div class="form-group"><input type="tel" id="telefono" placeholder="Teléfono *"></div>
            <div class="form-group"><input type="text" id="direccion" placeholder="Dirección *"></div>
            <div class="form-group"><input type="text" id="referencia" placeholder="Referencia (portón, color casa)"></div>
            <div class="form-group"><textarea id="notas" rows="2" placeholder="Notas (sin cebolla, etc.)"></textarea></div>
            <button class="btn-submit" onclick="enviarPedido()">ENVIAR PEDIDO 🌭</button>
        </div>
    </div>
</div>

<!-- FLOATING BAR -->
<div class="float-bar" id="floatBar">
    <div class="float-info">
        <small>Total</small>
        <strong id="floatTotal">$0</strong>
    </div>
    <button onclick="toggleCart()">VER PEDIDO</button>
</div>

<div class="toast" id="toast">¡AGREGADO! 🐶</div>

<!-- FOOTER -->
<footer class="footer" id="contacto">
    <div class="footer-logo">la perrera</div>
    <p>Hot Dogs Muy Perros</p>
    <h3>ENCUÉNTRANOS</h3>
    <p>WhatsApp: 413-100-3958</p>
    <p>Facebook: La Perrera</p>
    <p>Instagram: @laperrera2024</p>
    <h3>NAVEGA</h3>
    <a href="#menu">Menu</a>
    <a href="#contacto">Contacto</a>
    <a href="#nosotros">Nosotros</a>
    <div class="footer-copy">© 2024 La Perrera. Todos los derechos reservados.</div>
</footer>

<script>
const menu = [
    { id:1, cat:'HOT DOGS', nombre:'Chihuahua', desc:'Bien llenito de guacamole.', precio:60 },
    { id:2, cat:'HOT DOGS', nombre:'Pitbull', desc:'Cebollita caramelizada y un toquesito de BBQ.', precio:60 },
    { id:3, cat:'HOT DOGS', nombre:'Xolo', desc:'Chili de la casa (res, cerdo, frijoles) y chiles en vinagre.', precio:60 },
    { id:4, cat:'HOT DOGS', nombre:'Callejero', desc:'Jitomate, cebollita y jalapeño en vinagre.', precio:60 },
    { id:5, cat:'HOT DOGS', nombre:'Corgi', desc:'Cebolla caramelizada, piña y toque de chipotle.', precio:60 },
    { id:6, cat:'HAMBURGUESAS', nombre:'Bulldog', desc:'200gr res, queso americano, vegetales y pepinillos.', precio:100 },
    { id:7, cat:'HAMBURGUESAS', nombre:'Golden Retriever', desc:'Pollo crujiente, Monterrey Jack, salsa buffalo y jalapeño.', precio:100 },
    { id:8, cat:'HAMBURGUESAS', nombre:'Beagle', desc:'Pan bagel, doble carnita 100gr, quesos y cebollita caramelizada.', precio:100 },
    { id:9, cat:'HAMBURGUESAS', nombre:'Labrador', desc:'Pollo crujiente, tocino, Monterrey Jack, pepinillos y miel de chipetín.', precio:100 },
    { id:10, cat:'HAMBURGUESAS', nombre:'Doberman', desc:'Tocino, 200gr res, queso americano, cebollita y chilitos en vinagre.', precio:100 },
    { id:11, cat:'PAPAS', nombre:'Papas perronas', desc:'500gr papas, lemon pepper, queso, 200gr carne o pollo, aderezo y chiles.', precio:150 },
    { id:12, cat:'PAPAS', nombre:'Papas sencillas', desc:'250gr papas con lemon pepper.', precio:50 },
    { id:13, cat:'PAPAS', nombre:'Papas con pollo', desc:'Papas sencillas con pollo crujiente.', precio:90 },
    { id:14, cat:'PAPAS', nombre:'Papas con salchicha', desc:'Papas sencillas con salchicha polaca.', precio:80 },
    { id:15, cat:'PAPAS', nombre:'Papas dalmata', desc:'250gr papas, lemon pepper, queso cheddar y tocino.', precio:70 },
    { id:16, cat:'PAPAS', nombre:'Papas Gajo', desc:'300gr papas de gajo con lemon pepper.', precio:60 },
    { id:17, cat:'PAPAS', nombre:'Dedos de queso', desc:'6 dedos de queso mozzarella.', precio:60 },
    { id:18, cat:'BEBIDAS', nombre:'Refresco 2L', desc:'Coca-Cola familiar.', precio:30 },
    { id:19, cat:'ADICIONALES', nombre:'Salchicha polaca', desc:'Extra de salchicha.', precio:30 },
    { id:20, cat:'ADICIONALES', nombre:'Pechuga crujiente', desc:'Extra de pechuga.', precio:40 },
    { id:21, cat:'ADICIONALES', nombre:'Guacamole', desc:'Extra de guacamole.', precio:15 }
];

let carrito = [];

function renderMenu() {
    const cats = [...new Set(menu.map(p => p.cat))];
    document.getElementById('catNav').innerHTML = cats.map((c,i) =>
        `<a href="#cat-${i}" class="cat-pill${i===0?' active':''}">${c}</a>`
    ).join('');

    document.getElementById('menu').innerHTML = cats.map((cat,i) => `
        <div class="cat-section" id="cat-${i}">
            <h2 class="cat-title">${cat}</h2>
            ${menu.filter(p=>p.cat===cat).map(p=>`
                <div class="producto">
                    <div class="producto-info">
                        <h3>${p.nombre}</h3>
                        <p>${p.desc}</p>
                        <div class="producto-precio">$${p.precio}</div>
                    </div>
                    <button class="btn-add" onclick="agregar(${p.id})">+</button>
                </div>
            `).join('')}
        </div>
    `).join('');
}

function agregar(id) {
    const prod = menu.find(p => p.id === id);
    const item = carrito.find(i => i.id === id);
    if (item) item.cantidad++;
    else carrito.push({ ...prod, cantidad: 1 });
    actualizarCarrito();
    toast(`¡${prod.nombre} agregado!`);
}

function actualizarCarrito() {
    const total = carrito.reduce((s,i)=>s+i.precio*i.cantidad,0);
    const count = carrito.reduce((s,i)=>s+i.cantidad,0);

    document.getElementById('cartTotal').textContent = `$${total}`;
    document.getElementById('floatTotal').textContent = `$${total}`;

    const bar = document.getElementById('floatBar');
    count > 0 ? bar.classList.add('visible') : bar.classList.remove('visible');

    const cont = document.getElementById('cartItems');
    if (carrito.length === 0) {
        cont.innerHTML = '<div class="cart-empty">TU CARRITO ESTÁ VACÍO 🐶</div>';
    } else {
        cont.innerHTML = carrito.map((item,i)=>`
            <div class="cart-item">
                <div>
                    <h4>${item.nombre}</h4>
                    <small>$${item.precio} c/u</small>
                </div>
                <div class="qty-group">
                    <button class="qty-btn" onclick="cambiar(${i},-1)">−</button>
                    <span class="qty-num">${item.cantidad}</span>
                    <button class="qty-btn" onclick="cambiar(${i},1)">+</button>
                </div>
                <div class="cart-item-price">$${item.precio*item.cantidad}</div>
            </div>
        `).join('');
    }
}

function cambiar(i,d) {
    carrito[i].cantidad += d;
    if (carrito[i].cantidad <= 0) carrito.splice(i,1);
    actualizarCarrito();
}

function toggleCart() {
    document.getElementById('cartPanel').classList.toggle('open');
    document.getElementById('cartOverlay').classList.toggle('open');
}

function toggleMobile() {
    document.getElementById('mobileMenu').classList.toggle('open');
}

function toast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(()=>t.classList.remove('show'), 1500);
}

function enviarPedido() {
    const nombre = document.getElementById('nombre').value.trim();
    const telefono = document.getElementById('telefono').value.trim();
    const direccion = document.getElementById('direccion').value.trim();
    const referencia = document.getElementById('referencia').value.trim();
    const notas = document.getElementById('notas').value.trim();

    if (carrito.length === 0) { toast('AGREGA ALGO PRIMERO'); return; }
    if (!nombre || !telefono || !direccion) { toast('FALTAN DATOS'); return; }

    const pedido = {
        id: Date.now(),
        fecha: new Date().toLocaleString('es-MX'),
        cliente: { nombre, telefono, direccion, referencia, notas },
        items: carrito,
        total: carrito.reduce((s,i)=>s+i.precio*i.cantidad,0)
    };

    const g = JSON.parse(localStorage.getItem('pedidosLaPerrera')) || [];
    g.push(pedido);
    localStorage.setItem('pedidosLaPerrera', JSON.stringify(g));

    carrito = [];
    actualizarCarrito();
    toggleCart();
    ['nombre','telefono','direccion','referencia','notas'].forEach(id=>document.getElementById(id).value='');
    toast('¡PEDIDO ENVIADO! 🌭');
}

window.addEventListener('scroll', () => {
    const secs = document.querySelectorAll('.cat-section');
    const pills = document.querySelectorAll('.cat-pill');
    let active = 0;
    secs.forEach((s,i)=>{ if (s.getBoundingClientRect().top < 220) active = i; });
    pills.forEach((p,i)=>p.classList.toggle('active', i===active));
});

renderMenu();
actualizarCarrito();
</script>
</body>
</html>
