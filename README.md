<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FutCancha – Reserva tu Cancha Sintética</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root {
    --verde:       #1B6B35;
    --verde2:      #2E8B57;
    --verde3:      #4CAF50;
    --verde-light: #E8F5E9;
    --verde-mid:   #C8E6C9;
    --verde-hover: #145228;
    --rojo:        #D32F2F;
    --rojo-light:  #FFEBEE;
    --amarillo:    #F57F17;
    --amarillo-light: #FFF9C4;
    --azul:        #1565C0;
    --azul-light:  #E3F2FD;
    --gris1:       #F8F9FA;
    --gris2:       #ECEFF1;
    --gris3:       #B0BEC5;
    --texto:       #1A1A2E;
    --texto2:      #546E7A;
    --blanco:      #FFFFFF;
    --sombra:      0 4px 20px rgba(0,0,0,0.12);
    --radio:       14px;
    --radio-sm:    10px;
  }

  body {
    font-family: 'Inter', 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #0D3B1E 0%, #1B6B35 40%, #2E8B57 100%);
    min-height: 100vh;
    padding: 40px 20px 60px;
  }

  /* HEADER PAGE */
  .page-header {
    text-align: center;
    color: #fff;
    margin-bottom: 40px;
  }
  .page-header h1 {
    font-size: 32px;
    font-weight: 800;
    letter-spacing: -0.5px;
    margin-bottom: 6px;
  }
  .page-header p { font-size: 15px; opacity: 0.85; font-weight: 400; }
  .logo-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(255,255,255,0.15);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.3);
    border-radius: 50px;
    padding: 8px 20px;
    margin-bottom: 20px;
    color: #fff;
    font-size: 13px;
    font-weight: 600;
  }
  .logo-badge .dot { width: 8px; height: 8px; background: #4CAF50; border-radius: 50%; animation: pulse 1.5s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.6;transform:scale(1.3)} }

  /* DEVICE GRID */
  .device-grid {
    display: flex;
    gap: 28px;
    justify-content: center;
    flex-wrap: wrap;
    max-width: 1700px;
    margin: 0 auto;
  }

  .device-col { display: flex; flex-direction: column; align-items: center; gap: 14px; }
  .device-label {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.75);
    text-align: center;
  }

  /* PHONE FRAME */
  .phone {
    width: 375px;
    background: var(--blanco);
    border-radius: 44px;
    box-shadow: 0 30px 80px rgba(0,0,0,0.45), 0 0 0 10px #111, 0 0 0 11px #333;
    overflow: hidden;
    position: relative;
    height: 780px;
    display: flex;
    flex-direction: column;
  }

  /* NOTCH */
  .notch {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 126px;
    height: 34px;
    background: #111;
    border-radius: 0 0 20px 20px;
    z-index: 100;
  }

  /* STATUS BAR */
  .status-bar {
    background: var(--verde);
    height: 44px;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    padding: 0 24px 8px;
    flex-shrink: 0;
  }
  .status-bar .time { color: #fff; font-size: 13px; font-weight: 700; }
  .status-bar .icons { color: #fff; font-size: 11px; display: flex; gap: 6px; align-items: center; }

  /* APP BAR */
  .app-bar {
    background: var(--verde);
    padding: 10px 18px 14px;
    display: flex;
    align-items: center;
    gap: 10px;
    flex-shrink: 0;
  }
  .app-bar .back-btn {
    width: 34px; height: 34px;
    background: rgba(255,255,255,0.18);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    cursor: pointer; color: #fff; font-size: 17px;
    transition: background .15s;
  }
  .app-bar .back-btn:hover { background: rgba(255,255,255,0.28); }
  .app-bar .title { color: #fff; font-size: 18px; font-weight: 700; flex: 1; }
  .app-bar .subtitle { color: rgba(255,255,255,0.75); font-size: 12px; font-weight: 400; }
  .app-bar .avatar {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: rgba(255,255,255,0.22);
    border: 2px solid rgba(255,255,255,0.4);
    display: flex; align-items: center; justify-content: center;
    color: #fff; font-size: 17px;
  }
  .app-bar .notif-btn {
    width: 34px; height: 34px;
    background: rgba(255,255,255,0.18);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    cursor: pointer; color: #fff; font-size: 16px;
    position: relative;
  }
  .notif-dot {
    position: absolute;
    top: 6px; right: 6px;
    width: 8px; height: 8px;
    background: #FF5252;
    border-radius: 50%;
    border: 2px solid var(--verde);
  }

  /* SCROLLABLE CONTENT */
  .screen {
    flex: 1;
    overflow-y: auto;
    background: var(--gris1);
  }
  .screen::-webkit-scrollbar { width: 3px; }
  .screen::-webkit-scrollbar-thumb { background: var(--gris3); border-radius: 2px; }

  /* BOTTOM NAV */
  .bottom-nav {
    background: var(--blanco);
    border-top: 1px solid var(--gris2);
    display: flex;
    padding: 8px 0 16px;
    flex-shrink: 0;
  }
  .nav-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;
    cursor: pointer;
    padding: 4px 0;
  }
  .nav-icon {
    font-size: 22px;
    opacity: 0.4;
    transition: all .15s;
  }
  .nav-icon.active { opacity: 1; }
  .nav-text {
    font-size: 10px;
    font-weight: 600;
    color: var(--gris3);
    transition: all .15s;
  }
  .nav-text.active { color: var(--verde); }
  .nav-dot {
    width: 4px; height: 4px;
    background: var(--verde);
    border-radius: 50%;
    margin-top: 2px;
  }

  /* ==================== PANTALLA 1: HOME ==================== */
  .hero-banner {
    background: linear-gradient(135deg, #1B6B35 0%, #2E8B57 100%);
    padding: 18px 18px 24px;
    position: relative;
    overflow: hidden;
  }
  .hero-banner::before {
    content: '⚽';
    position: absolute;
    right: -10px;
    bottom: -10px;
    font-size: 90px;
    opacity: 0.12;
    transform: rotate(-15deg);
  }
  .hero-greeting { color: rgba(255,255,255,0.8); font-size: 13px; font-weight: 400; margin-bottom: 2px; }
  .hero-name { color: #fff; font-size: 21px; font-weight: 800; margin-bottom: 14px; }
  .search-box {
    background: #fff;
    border-radius: 12px;
    display: flex;
    align-items: center;
    padding: 10px 14px;
    gap: 10px;
    box-shadow: 0 4px 16px rgba(0,0,0,0.2);
  }
  .search-box span { font-size: 17px; opacity: 0.5; }
  .search-box input {
    flex: 1; border: none; outline: none;
    font-size: 14px; color: var(--texto);
    font-family: inherit; background: transparent;
  }
  .search-box input::placeholder { color: var(--gris3); }
  .search-box .mic { font-size: 16px; color: var(--verde2); }

  .chips-row {
    display: flex;
    gap: 8px;
    padding: 14px 18px 10px;
    overflow-x: auto;
  }
  .chips-row::-webkit-scrollbar { display: none; }
  .chip {
    border-radius: 50px;
    padding: 7px 16px;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    white-space: nowrap;
    border: 1.5px solid var(--gris2);
    background: var(--blanco);
    color: var(--texto2);
    transition: all .15s;
  }
  .chip.active {
    background: var(--verde);
    color: #fff;
    border-color: var(--verde);
  }

  .section-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 18px 8px;
  }
  .section-header h3 { font-size: 15px; font-weight: 700; color: var(--texto); }
  .section-header a { font-size: 12px; color: var(--verde2); font-weight: 600; text-decoration: none; }

  /* CANCHA CARD - alta fidelidad */
  .cancha-card {
    margin: 0 18px 14px;
    border-radius: var(--radio);
    box-shadow: 0 2px 12px rgba(0,0,0,0.08);
    background: var(--blanco);
    overflow: hidden;
    cursor: pointer;
    transition: all .2s;
    border: 1px solid var(--gris2);
  }
  .cancha-card:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,0,0,0.14); }

  .cancha-img-hf {
    height: 140px;
    position: relative;
    overflow: hidden;
  }
  .field-bg {
    width: 100%; height: 100%;
    background: linear-gradient(160deg, #1B5E20 0%, #2E7D32 35%, #388E3C 60%, #1B5E20 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }
  /* Mini campo de fútbol SVG */
  .mini-field {
    width: 130px; height: 80px;
    border: 2.5px solid rgba(255,255,255,0.5);
    border-radius: 4px;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .mini-field::before {
    content: '';
    width: 44px; height: 44px;
    border: 2px solid rgba(255,255,255,0.4);
    border-radius: 50%;
    position: absolute;
  }
  .mini-field::after {
    content: '';
    width: 2px; height: 100%;
    background: rgba(255,255,255,0.4);
    position: absolute;
  }
  .center-dot {
    width: 6px; height: 6px;
    background: rgba(255,255,255,0.7);
    border-radius: 50%;
    position: absolute;
    z-index: 1;
  }
  .left-goal {
    position: absolute; left: 0; top: 50%;
    transform: translateY(-50%);
    width: 16px; height: 32px;
    border: 2px solid rgba(255,255,255,0.45);
    border-left: none;
    border-radius: 0 3px 3px 0;
  }
  .right-goal {
    position: absolute; right: 0; top: 50%;
    transform: translateY(-50%);
    width: 16px; height: 32px;
    border: 2px solid rgba(255,255,255,0.45);
    border-right: none;
    border-radius: 3px 0 0 3px;
  }

  .badge-disponible {
    position: absolute; top: 10px; right: 10px;
    background: rgba(255,255,255,0.92);
    color: var(--verde);
    font-size: 11px; font-weight: 700;
    padding: 4px 10px; border-radius: 50px;
    display: flex; align-items: center; gap: 4px;
  }
  .badge-disponible .dot-green {
    width: 6px; height: 6px;
    background: #4CAF50; border-radius: 50%;
  }
  .badge-ocupado {
    position: absolute; top: 10px; right: 10px;
    background: rgba(255,255,255,0.92);
    color: var(--rojo);
    font-size: 11px; font-weight: 700;
    padding: 4px 10px; border-radius: 50px;
  }
  .badge-num {
    position: absolute; top: 10px; left: 10px;
    background: rgba(0,0,0,0.45);
    color: #fff;
    font-size: 10px; font-weight: 700;
    padding: 3px 8px; border-radius: 50px;
    backdrop-filter: blur(4px);
  }
  .fav-btn {
    position: absolute; bottom: 10px; right: 10px;
    background: rgba(255,255,255,0.9);
    border-radius: 50%;
    width: 30px; height: 30px;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px; cursor: pointer;
    box-shadow: 0 2px 6px rgba(0,0,0,0.2);
  }

  .cancha-body { padding: 14px 14px 12px; }
  .cancha-row1 { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 6px; }
  .cancha-name { font-size: 15px; font-weight: 700; color: var(--texto); }
  .cancha-rating {
    display: flex; align-items: center; gap: 3px;
    font-size: 12px; font-weight: 600; color: var(--amarillo);
  }
  .cancha-rating span { color: var(--texto2); }
  .cancha-location { font-size: 12px; color: var(--texto2); margin-bottom: 10px; display: flex; align-items: center; gap: 4px; }
  .cancha-tags { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 10px; }
  .ctag {
    background: var(--verde-light);
    color: var(--verde);
    font-size: 10px; font-weight: 600;
    padding: 3px 9px; border-radius: 20px;
  }
  .cancha-footer {
    display: flex; align-items: center; justify-content: space-between;
    padding-top: 10px; border-top: 1px solid var(--gris2);
  }
  .precio-block { display: flex; flex-direction: column; }
  .precio-val { font-size: 18px; font-weight: 800; color: var(--verde); line-height: 1; }
  .precio-sub { font-size: 10px; color: var(--texto2); font-weight: 400; }
  .btn-reservar-hf {
    background: var(--verde);
    color: #fff;
    border: none;
    border-radius: 10px;
    padding: 10px 20px;
    font-size: 13px; font-weight: 700;
    cursor: pointer;
    transition: background .15s;
    font-family: inherit;
  }
  .btn-reservar-hf:hover { background: var(--verde-hover); }

  /* ==================== PANTALLA 2: DETALLE ==================== */
  .detalle-img {
    height: 200px;
    background: linear-gradient(160deg, #1B5E20 0%, #2E7D32 50%, #388E3C 100%);
    position: relative;
    display: flex; align-items: center; justify-content: center;
  }
  .detalle-img .big-field {
    width: 200px; height: 120px;
    border: 3px solid rgba(255,255,255,0.5);
    border-radius: 6px;
    position: relative;
    display: flex; align-items: center; justify-content: center;
  }
  .big-field::before {
    content: '';
    width: 66px; height: 66px;
    border: 2.5px solid rgba(255,255,255,0.4);
    border-radius: 50%;
    position: absolute;
  }
  .big-field::after {
    content: '';
    width: 2.5px; height: 100%;
    background: rgba(255,255,255,0.4);
    position: absolute;
  }
  .detalle-img .img-overlay {
    position: absolute; bottom: 0; left: 0; right: 0;
    background: linear-gradient(to top, rgba(0,0,0,0.5), transparent);
    padding: 14px 18px 12px;
    display: flex; justify-content: space-between; align-items: flex-end;
  }
  .detalle-nombre { color: #fff; font-size: 20px; font-weight: 800; }
  .detalle-rating { display: flex; align-items: center; gap: 4px; color: #FFD54F; font-size: 13px; font-weight: 600; }

  .info-pills {
    display: flex; gap: 8px;
    padding: 14px 18px 10px;
    overflow-x: auto;
  }
  .info-pills::-webkit-scrollbar { display: none; }
  .info-pill {
    display: flex; flex-direction: column; align-items: center;
    background: var(--blanco);
    border: 1px solid var(--gris2);
    border-radius: 12px;
    padding: 10px 16px;
    min-width: 80px;
    gap: 3px;
  }
  .info-pill .pill-icon { font-size: 18px; }
  .info-pill .pill-val { font-size: 13px; font-weight: 700; color: var(--texto); }
  .info-pill .pill-label { font-size: 10px; color: var(--texto2); font-weight: 500; }

  /* CALENDARIO ALTA FIDELIDAD */
  .cal-container { margin: 0 18px 14px; background: var(--blanco); border-radius: var(--radio); border: 1px solid var(--gris2); overflow: hidden; }
  .cal-top {
    background: var(--verde);
    padding: 12px 16px;
    display: flex; align-items: center; justify-content: space-between;
  }
  .cal-top h3 { color: #fff; font-size: 14px; font-weight: 700; }
  .cal-nav-btn { background: rgba(255,255,255,0.2); border: none; border-radius: 8px; width: 28px; height: 28px; color: #fff; font-size: 13px; cursor: pointer; display: flex; align-items: center; justify-content: center; }
  .cal-body { padding: 12px 12px 14px; }
  .cal-days-row { display: grid; grid-template-columns: repeat(7, 1fr); gap: 3px; margin-bottom: 6px; }
  .cal-day-name { text-align: center; font-size: 10px; font-weight: 700; color: var(--texto2); padding: 4px 0; text-transform: uppercase; }
  .cal-dates-grid { display: grid; grid-template-columns: repeat(7, 1fr); gap: 3px; }
  .cal-date {
    aspect-ratio: 1;
    border-radius: 8px;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    font-size: 12px; font-weight: 600;
    cursor: pointer;
    transition: all .15s;
    position: relative;
  }
  .cal-date.empty { background: transparent; cursor: default; }
  .cal-date.past { color: var(--gris3); background: transparent; cursor: not-allowed; }
  .cal-date.disponible { background: var(--verde-light); color: var(--verde); }
  .cal-date.disponible:hover { background: var(--verde); color: #fff; }
  .cal-date.poco { background: var(--amarillo-light); color: var(--amarillo); }
  .cal-date.ocupado { background: var(--rojo-light); color: var(--rojo); cursor: not-allowed; }
  .cal-date.hoy { border: 2px solid var(--verde2); }
  .cal-date.selected { background: var(--verde) !important; color: #fff !important; }
  .cal-date .mini-dot { width: 4px; height: 4px; border-radius: 50%; position: absolute; bottom: 3px; }
  .cal-date.disponible .mini-dot { background: var(--verde); }
  .cal-date.poco .mini-dot { background: var(--amarillo); }
  .cal-date.selected .mini-dot { background: #fff; }

  .cal-legend {
    display: flex; gap: 14px; padding: 10px 14px 12px;
    background: var(--gris1);
    border-top: 1px solid var(--gris2);
  }
  .legend-item { display: flex; align-items: center; gap: 5px; }
  .legend-dot { width: 10px; height: 10px; border-radius: 3px; }
  .legend-item span { font-size: 10px; color: var(--texto2); font-weight: 500; }

  /* HORARIOS ALTA FIDELIDAD */
  .horarios-container { margin: 0 18px 14px; }
  .horarios-container h3 { font-size: 14px; font-weight: 700; color: var(--texto); margin-bottom: 10px; display: flex; align-items: center; gap: 8px; }
  .horarios-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }
  .hora-slot {
    background: var(--blanco);
    border: 1.5px solid var(--gris2);
    border-radius: 10px;
    padding: 10px 6px;
    text-align: center;
    cursor: pointer;
    transition: all .15s;
  }
  .hora-slot.libre { background: var(--verde-light); border-color: #A5D6A7; }
  .hora-slot.libre:hover, .hora-slot.libre.selected { background: var(--verde); border-color: var(--verde); }
  .hora-slot.libre:hover .h-time, .hora-slot.libre.selected .h-time { color: #fff; }
  .hora-slot.libre:hover .h-price, .hora-slot.libre.selected .h-price { color: rgba(255,255,255,0.8); }
  .hora-slot.ocupado { background: var(--rojo-light); border-color: #FFCDD2; cursor: not-allowed; opacity: 0.7; }
  .hora-slot.poco { background: var(--amarillo-light); border-color: #FFE082; }
  .h-time { font-size: 12px; font-weight: 700; color: var(--texto); }
  .h-label { font-size: 10px; color: var(--texto2); margin: 2px 0; }
  .hora-slot.libre .h-time { color: var(--verde); }
  .hora-slot.ocupado .h-time { color: var(--rojo); }
  .hora-slot.poco .h-time { color: var(--amarillo); }
  .h-price { font-size: 10px; font-weight: 600; color: var(--verde); }

  /* FORMULARIO ALTA FIDELIDAD */
  .form-container { padding: 0 18px 14px; }
  .form-card {
    background: var(--blanco);
    border-radius: var(--radio);
    border: 1px solid var(--gris2);
    overflow: hidden;
  }
  .form-card-header {
    background: linear-gradient(90deg, var(--verde), var(--verde2));
    padding: 12px 16px;
    color: #fff;
    font-size: 14px; font-weight: 700;
    display: flex; align-items: center; gap: 8px;
  }
  .form-body { padding: 16px; }
  .form-group { margin-bottom: 14px; }
  .form-group label {
    display: block; font-size: 11px; font-weight: 700;
    color: var(--texto2); margin-bottom: 6px;
    text-transform: uppercase; letter-spacing: 0.5px;
  }
  .form-input {
    width: 100%;
    border: 1.5px solid var(--gris2);
    border-radius: 10px;
    padding: 11px 14px;
    font-size: 14px; color: var(--texto);
    background: var(--gris1);
    outline: none;
    font-family: inherit;
    transition: all .15s;
  }
  .form-input:focus { border-color: var(--verde); background: #fff; }
  .form-input::placeholder { color: var(--gris3); }
  .input-with-icon { position: relative; }
  .input-with-icon .form-input { padding-left: 40px; }
  .input-with-icon .input-icon {
    position: absolute; left: 12px; top: 50%;
    transform: translateY(-50%);
    font-size: 17px; opacity: 0.5;
  }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }

  /* PAGO MÉTODOS */
  .pago-opciones { display: flex; flex-direction: column; gap: 8px; }
  .pago-opcion {
    border: 1.5px solid var(--gris2);
    border-radius: 10px;
    padding: 12px 14px;
    display: flex; align-items: center; gap: 12px;
    cursor: pointer;
    transition: all .15s;
    background: var(--gris1);
  }
  .pago-opcion.selected { border-color: var(--verde); background: var(--verde-light); }
  .pago-opcion .pago-icon { font-size: 22px; }
  .pago-info { flex: 1; }
  .pago-nombre { font-size: 13px; font-weight: 700; color: var(--texto); }
  .pago-desc { font-size: 11px; color: var(--texto2); }
  .radio-circle {
    width: 18px; height: 18px;
    border: 2px solid var(--gris3);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
  }
  .pago-opcion.selected .radio-circle { border-color: var(--verde); }
  .radio-dot { width: 8px; height: 8px; background: var(--verde); border-radius: 50%; }

  /* RESUMEN CARD */
  .resumen-hf {
    margin: 0 18px 14px;
    background: var(--blanco);
    border-radius: var(--radio);
    border: 1.5px solid var(--verde-mid);
    overflow: hidden;
  }
  .resumen-header {
    background: linear-gradient(90deg, var(--verde), var(--verde2));
    padding: 12px 16px;
    color: #fff; font-size: 14px; font-weight: 700;
    display: flex; align-items: center; gap: 8px;
  }
  .resumen-body { padding: 14px 16px; }
  .resumen-row {
    display: flex; justify-content: space-between;
    align-items: center; padding: 8px 0;
    border-bottom: 1px solid var(--gris2);
  }
  .resumen-row:last-child { border-bottom: none; }
  .r-label { font-size: 12px; color: var(--texto2); display: flex; align-items: center; gap: 6px; }
  .r-val { font-size: 13px; font-weight: 700; color: var(--texto); }
  .r-val.price { color: var(--verde); font-size: 18px; }
  .r-val.pago-tag {
    background: var(--azul-light); color: var(--azul);
    padding: 3px 10px; border-radius: 20px;
    font-size: 11px;
  }

  /* BOTONES PRINCIPALES */
  .btn-main {
    display: block;
    width: calc(100% - 36px);
    margin: 0 18px 10px;
    background: var(--verde);
    color: #fff; border: none;
    border-radius: 12px;
    padding: 15px;
    font-size: 16px; font-weight: 700;
    cursor: pointer; text-align: center;
    transition: all .15s;
    font-family: inherit;
    box-shadow: 0 4px 14px rgba(27,107,53,0.35);
  }
  .btn-main:hover { background: var(--verde-hover); transform: translateY(-1px); }
  .btn-secondary-hf {
    display: block;
    width: calc(100% - 36px);
    margin: 0 18px 10px;
    background: var(--blanco);
    color: var(--verde); border: 2px solid var(--verde);
    border-radius: 12px;
    padding: 13px;
    font-size: 15px; font-weight: 700;
    cursor: pointer; text-align: center;
    transition: all .15s;
    font-family: inherit;
  }

  /* CONFIRMACIÓN */
  .confirm-screen {
    padding: 28px 18px;
    display: flex; flex-direction: column; align-items: center;
    background: var(--gris1);
  }
  .confirm-anim {
    width: 90px; height: 90px;
    background: linear-gradient(135deg, var(--verde), var(--verde2));
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 44px;
    margin-bottom: 18px;
    box-shadow: 0 8px 28px rgba(27,107,53,0.35);
    animation: pop .4s cubic-bezier(0.34,1.56,0.64,1);
  }
  @keyframes pop { from{transform:scale(0)} to{transform:scale(1)} }
  .confirm-title { font-size: 22px; font-weight: 800; color: var(--texto); margin-bottom: 6px; text-align: center; }
  .confirm-sub { font-size: 13px; color: var(--texto2); text-align: center; margin-bottom: 22px; line-height: 1.5; }

  .codigo-box-hf {
    background: linear-gradient(135deg, var(--verde), var(--verde2));
    border-radius: 14px;
    padding: 16px 24px;
    text-align: center;
    margin-bottom: 20px;
    width: 100%;
    box-shadow: 0 6px 20px rgba(27,107,53,0.3);
  }
  .codigo-label { color: rgba(255,255,255,0.8); font-size: 11px; font-weight: 600; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 4px; }
  .codigo-val { color: #fff; font-size: 28px; font-weight: 800; letter-spacing: 3px; }

  .share-btns { display: flex; gap: 10px; width: 100%; margin-bottom: 16px; }
  .share-btn {
    flex: 1; background: var(--blanco);
    border: 1.5px solid var(--gris2);
    border-radius: 10px; padding: 10px 8px;
    text-align: center; cursor: pointer;
    font-size: 11px; font-weight: 700; color: var(--texto2);
    display: flex; flex-direction: column; align-items: center; gap: 4px;
    transition: all .15s;
  }
  .share-btn:hover { border-color: var(--verde); color: var(--verde); }
  .share-btn span { font-size: 20px; }

  .cancel-note { font-size: 11px; color: var(--texto2); text-align: center; }

  /* ==================== PANTALLA 5: ADMIN ==================== */
  .admin-header {
    background: linear-gradient(135deg, #0D3B1E, #1B6B35);
    padding: 14px 18px 18px;
  }
  .admin-welcome { color: rgba(255,255,255,0.75); font-size: 12px; margin-bottom: 2px; }
  .admin-name { color: #fff; font-size: 18px; font-weight: 800; margin-bottom: 14px; }
  .stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
  .stat-card {
    background: rgba(255,255,255,0.12);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 12px;
    padding: 12px 10px;
    text-align: center;
  }
  .stat-num { color: #fff; font-size: 22px; font-weight: 800; line-height: 1; }
  .stat-label { color: rgba(255,255,255,0.7); font-size: 10px; font-weight: 500; margin-top: 3px; }

  .agenda-section { padding: 14px 18px 8px; }
  .agenda-section h3 { font-size: 15px; font-weight: 700; color: var(--texto); margin-bottom: 12px; display: flex; align-items: center; gap: 8px; }

  .reserva-item-hf {
    background: var(--blanco);
    border: 1px solid var(--gris2);
    border-radius: 12px;
    padding: 12px 14px;
    margin-bottom: 8px;
    display: flex; align-items: center; gap: 12px;
    transition: all .15s;
    cursor: pointer;
  }
  .reserva-item-hf:hover { box-shadow: 0 4px 14px rgba(0,0,0,0.1); transform: translateY(-1px); }
  .hora-badge {
    background: var(--gris2);
    border-radius: 8px; padding: 8px 10px;
    text-align: center; min-width: 58px;
  }
  .hora-badge .h { font-size: 14px; font-weight: 800; color: var(--texto); }
  .hora-badge .m { font-size: 10px; color: var(--texto2); }
  .reserva-info-hf { flex: 1; }
  .r-nombre { font-size: 14px; font-weight: 700; color: var(--texto); }
  .r-detalle { font-size: 11px; color: var(--texto2); margin-top: 2px; display: flex; align-items: center; gap: 6px; }
  .status-badge {
    padding: 4px 10px; border-radius: 20px;
    font-size: 10px; font-weight: 700;
    white-space: nowrap;
  }
  .status-badge.confirmada { background: var(--verde-light); color: var(--verde); }
  .status-badge.pendiente { background: var(--amarillo-light); color: var(--amarillo); }
  .status-badge.libre { background: var(--gris2); color: var(--texto2); border: 1px dashed var(--gris3); }

  /* PROGRESS STEPS */
  .progress-bar {
    display: flex; align-items: center;
    padding: 14px 18px 10px;
    background: var(--blanco);
    border-bottom: 1px solid var(--gris2);
  }
  .step-item { display: flex; flex-direction: column; align-items: center; flex: 1; position: relative; }
  .step-item:not(:last-child)::after {
    content: '';
    position: absolute;
    top: 13px;
    left: 60%;
    width: 80%;
    height: 2px;
    background: var(--gris2);
    z-index: 0;
  }
  .step-item.done:not(:last-child)::after { background: var(--verde); }
  .step-circle {
    width: 26px; height: 26px;
    border-radius: 50%;
    background: var(--gris2);
    color: var(--gris3);
    display: flex; align-items: center; justify-content: center;
    font-size: 11px; font-weight: 700;
    z-index: 1;
    transition: all .2s;
  }
  .step-item.done .step-circle { background: var(--verde); color: #fff; }
  .step-item.active .step-circle { background: var(--verde); color: #fff; box-shadow: 0 0 0 3px var(--verde-mid); }
  .step-label { font-size: 9px; font-weight: 600; color: var(--gris3); margin-top: 4px; text-align: center; }
  .step-item.done .step-label, .step-item.active .step-label { color: var(--verde); }

  /* MAPA SCREEN */
  .mapa-container {
    background: var(--blanco);
    margin: 14px 18px;
    border-radius: var(--radio);
    overflow: hidden;
    border: 1px solid var(--gris2);
    height: 200px;
    display: flex; align-items: center; justify-content: center;
    position: relative;
    background: linear-gradient(135deg, #e8f0f8 0%, #d4e4f7 100%);
  }
  .mapa-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(150,180,210,0.3) 1px, transparent 1px),
      linear-gradient(90deg, rgba(150,180,210,0.3) 1px, transparent 1px);
    background-size: 30px 30px;
  }
  .mapa-road-h {
    position: absolute; left: 0; right: 0;
    height: 8px; background: rgba(200,210,220,0.8);
  }
  .mapa-road-v {
    position: absolute; top: 0; bottom: 0;
    width: 8px; background: rgba(200,210,220,0.8);
  }
  .mapa-pin {
    position: absolute;
    display: flex; flex-direction: column; align-items: center;
    cursor: pointer;
    z-index: 10;
  }
  .mapa-pin .pin-bubble {
    background: var(--verde);
    color: #fff; font-size: 10px; font-weight: 700;
    padding: 4px 8px; border-radius: 20px;
    white-space: nowrap;
    box-shadow: 0 2px 8px rgba(27,107,53,0.4);
  }
  .mapa-pin .pin-arrow {
    width: 0; height: 0;
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    border-top: 6px solid var(--verde);
  }
  .mapa-pin.secondary .pin-bubble { background: #546E7A; }
  .mapa-pin.secondary .pin-arrow { border-top-color: #546E7A; }

  /* ENCUESTA dentro del prototipo */
  .encuesta-screen {
    background: var(--gris1);
    padding: 16px 18px;
  }
  .encuesta-progress {
    background: var(--gris2);
    height: 4px; border-radius: 2px;
    margin-bottom: 16px;
    overflow: hidden;
  }
  .encuesta-progress .bar { height: 100%; background: var(--verde); border-radius: 2px; transition: width .4s; }
  .encuesta-card {
    background: var(--blanco);
    border-radius: var(--radio);
    border: 1px solid var(--gris2);
    padding: 16px;
    margin-bottom: 12px;
  }
  .q-num { font-size: 11px; font-weight: 700; color: var(--verde); text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 6px; }
  .q-text { font-size: 14px; font-weight: 600; color: var(--texto); margin-bottom: 12px; line-height: 1.4; }
  .q-options { display: flex; flex-direction: column; gap: 8px; }
  .q-option {
    border: 1.5px solid var(--gris2);
    border-radius: 10px; padding: 10px 14px;
    display: flex; align-items: center; gap: 10px;
    cursor: pointer; transition: all .15s;
    font-size: 13px; color: var(--texto);
  }
  .q-option.selected { border-color: var(--verde); background: var(--verde-light); color: var(--verde); font-weight: 600; }
  .q-option .opt-radio {
    width: 16px; height: 16px;
    border: 2px solid var(--gris3);
    border-radius: 50%; flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
  }
  .q-option.selected .opt-radio { border-color: var(--verde); }
  .opt-dot { width: 8px; height: 8px; background: var(--verde); border-radius: 50%; }

  /* BOTTOM SPACING */
  .spacer { height: 16px; }

  /* ======= FLUJO OVERVIEW ======= */
  .flow-overview {
    background: rgba(255,255,255,0.08);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 20px;
    padding: 20px 24px;
    max-width: 1700px;
    margin: 28px auto 0;
    color: #fff;
  }
  .flow-overview h2 { font-size: 16px; font-weight: 700; margin-bottom: 14px; opacity: 0.9; }
  .flow-steps { display: flex; gap: 10px; flex-wrap: wrap; align-items: center; }
  .flow-step {
    background: rgba(255,255,255,0.15);
    border-radius: 50px; padding: 8px 18px;
    font-size: 12px; font-weight: 700;
    display: flex; align-items: center; gap: 6px;
  }
  .flow-step.active { background: rgba(255,255,255,0.9); color: var(--verde); }
  .flow-arrow { opacity: 0.5; font-size: 16px; }
  .flow-meta { font-size: 11px; opacity: 0.6; margin-top: 10px; }
</style>
</head>
<body>

<!-- HEADER -->
<div class="page-header">
  <div class="logo-badge">
    <div class="dot"></div>
    Prototipo Alta Fidelidad – Tercer Corte
  </div>
  <h1>⚽ FutCancha</h1>
  <p>Sistema de Reservas de Canchas Sintéticas · IHC · Unicomfacauca 2025</p>
  <p style="margin-top:6px; font-size:13px; opacity:0.7;">Juan Sebastián Rojas Bravo · Juan Camilo Solarte Trochez</p>
</div>

<div class="device-grid">

  <!-- ============ PANTALLA 1: HOME / LISTADO ============ -->
  <div class="device-col">
    <div class="device-label">1. Pantalla Principal</div>
    <div class="phone">
      <div class="notch"></div>
      <div class="status-bar">
        <span class="time">9:41</span>
        <div class="icons"><span>📶</span><span>WiFi</span><span>🔋</span></div>
      </div>
      <div class="app-bar" style="padding-top:14px;">
        <div style="flex:1;">
          <div class="hero-greeting">Hola, Carlos 👋</div>
          <div class="hero-name" style="font-size:16px; margin-bottom:0;">¿Listo para jugar?</div>
        </div>
        <div class="notif-btn">🔔<div class="notif-dot"></div></div>
        <div class="avatar">👤</div>
      </div>
      <div class="screen">
        <div class="hero-banner">
          <div class="search-box">
            <span>🔍</span>
            <input type="text" placeholder="Buscar canchas cerca de ti..." readonly>
            <span class="mic">🎤</span>
          </div>
        </div>

        <div class="chips-row">
          <div class="chip active">📍 Todas</div>
          <div class="chip">⭐ Mejor valoradas</div>
          <div class="chip">💰 Precio</div>
          <div class="chip">🕐 Disponible ahora</div>
          <div class="chip">📏 Cerca de mí</div>
        </div>

        <div class="section-header">
          <h3>Canchas disponibles</h3>
          <a href="#">Ver mapa</a>
        </div>

        <!-- CARD 1 -->
        <div class="cancha-card">
          <div class="cancha-img-hf">
            <div class="field-bg">
              <div class="mini-field">
                <div class="center-dot"></div>
                <div class="left-goal"></div>
                <div class="right-goal"></div>
              </div>
            </div>
            <div class="badge-num">1 foto</div>
            <div class="badge-disponible"><div class="dot-green"></div> Disponible</div>
            <div class="fav-btn">🤍</div>
          </div>
          <div class="cancha-body">
            <div class="cancha-row1">
              <div class="cancha-name">Cancha El Bosque</div>
              <div class="cancha-rating">⭐ 4.8 <span>(124)</span></div>
            </div>
            <div class="cancha-location">📍 Barrio El Bosque · 0.8 km</div>
            <div class="cancha-tags">
              <span class="ctag">⚽ Fútbol 5</span>
              <span class="ctag">💡 Con luz</span>
              <span class="ctag">🚿 Vestuarios</span>
              <span class="ctag">🅿️ Parqueadero</span>
            </div>
            <div class="cancha-footer">
              <div class="precio-block">
                <div class="precio-val">$60.000</div>
                <div class="precio-sub">por hora</div>
              </div>
              <button class="btn-reservar-hf">Reservar →</button>
            </div>
          </div>
        </div>

        <!-- CARD 2 -->
        <div class="cancha-card">
          <div class="cancha-img-hf">
            <div class="field-bg" style="background:linear-gradient(160deg,#0D47A1 0%,#1565C0 50%,#1976D2 100%);">
              <div class="mini-field">
                <div class="center-dot"></div>
                <div class="left-goal"></div>
                <div class="right-goal"></div>
              </div>
            </div>
            <div class="badge-num">3 fotos</div>
            <div class="badge-disponible"><div class="dot-green"></div> Disponible</div>
            <div class="fav-btn">❤️</div>
          </div>
          <div class="cancha-body">
            <div class="cancha-row1">
              <div class="cancha-name">Cancha Los Pinos</div>
              <div class="cancha-rating">⭐ 4.6 <span>(87)</span></div>
            </div>
            <div class="cancha-location">📍 Los Pinos · 1.4 km</div>
            <div class="cancha-tags">
              <span class="ctag">⚽ Fútbol 7</span>
              <span class="ctag">💡 Con luz</span>
              <span class="ctag">🏆 Torneos</span>
            </div>
            <div class="cancha-footer">
              <div class="precio-block">
                <div class="precio-val">$80.000</div>
                <div class="precio-sub">por hora</div>
              </div>
              <button class="btn-reservar-hf">Reservar →</button>
            </div>
          </div>
        </div>

        <!-- CARD 3 ocupada -->
        <div class="cancha-card" style="opacity:0.7;">
          <div class="cancha-img-hf">
            <div class="field-bg" style="background:linear-gradient(160deg,#4a0000 0%,#7B1FA2 100%); filter:grayscale(30%);">
              <div class="mini-field">
                <div class="center-dot"></div>
                <div class="left-goal"></div>
                <div class="right-goal"></div>
              </div>
            </div>
            <div class="badge-ocupado">Ocupada ahora</div>
          </div>
          <div class="cancha-body">
            <div class="cancha-row1">
              <div class="cancha-name">Cancha Estadio Norte</div>
              <div class="cancha-rating">⭐ 4.9 <span>(203)</span></div>
            </div>
            <div class="cancha-location">📍 Estadio · 2.1 km</div>
            <div class="cancha-tags">
              <span class="ctag">⚽ Fútbol 11</span>
              <span class="ctag">🏟️ Graderías</span>
            </div>
            <div class="cancha-footer">
              <div class="precio-block">
                <div class="precio-val">$120.000</div>
                <div class="precio-sub">por hora</div>
              </div>
              <button class="btn-reservar-hf" disabled style="background:#ccc;cursor:not-allowed;">No disponible</button>
            </div>
          </div>
        </div>
        <div class="spacer"></div>
      </div>
      <div class="bottom-nav">
        <div class="nav-item"><div class="nav-icon active">🏠</div><div class="nav-text active">Inicio</div><div class="nav-dot"></div></div>
        <div class="nav-item"><div class="nav-icon">📅</div><div class="nav-text">Reservas</div></div>
        <div class="nav-item"><div class="nav-icon">🗺️</div><div class="nav-text">Mapa</div></div>
        <div class="nav-item"><div class="nav-icon">👤</div><div class="nav-text">Perfil</div></div>
      </div>
    </div>
  </div>

  <!-- ============ PANTALLA 2: DETALLE + DISPONIBILIDAD ============ -->
  <div class="device-col">
    <div class="device-label">2. Detalle de Cancha</div>
    <div class="phone">
      <div class="notch"></div>
      <div class="status-bar"><span class="time">9:43</span><div class="icons"><span>📶</span><span>WiFi</span><span>🔋</span></div></div>
      <div class="app-bar">
        <div class="back-btn">←</div>
        <div style="flex:1;"><div class="title" style="font-size:17px;">Cancha El Bosque</div></div>
        <div class="notif-btn">⋮</div>
      </div>
      <div class="screen">
        <!-- IMAGEN DETALLE -->
        <div class="detalle-img">
          <div class="big-field">
            <div class="center-dot"></div>
            <div style="position:absolute;width:2.5px;height:100%;background:rgba(255,255,255,0.4);"></div>
            <div style="position:absolute;left:0;top:50%;transform:translateY(-50%);width:22px;height:48px;border:2.5px solid rgba(255,255,255,0.45);border-left:none;border-radius:0 4px 4px 0;"></div>
            <div style="position:absolute;right:0;top:50%;transform:translateY(-50%);width:22px;height:48px;border:2.5px solid rgba(255,255,255,0.45);border-right:none;border-radius:4px 0 0 4px;"></div>
          </div>
          <div class="img-overlay">
            <div>
              <div class="detalle-nombre">El Bosque</div>
              <div style="color:rgba(255,255,255,0.8);font-size:12px;">📍 Barrio El Bosque · 0.8 km</div>
            </div>
            <div class="detalle-rating">⭐ 4.8 <span style="color:rgba(255,255,255,0.7);font-size:11px;">(124)</span></div>
          </div>
        </div>

        <!-- INFO PILLS -->
        <div class="info-pills">
          <div class="info-pill">
            <div class="pill-icon">⚽</div>
            <div class="pill-val">Fútbol 5</div>
            <div class="pill-label">Modalidad</div>
          </div>
          <div class="info-pill">
            <div class="pill-icon">📏</div>
            <div class="pill-val">20×40m</div>
            <div class="pill-label">Dimensiones</div>
          </div>
          <div class="info-pill">
            <div class="pill-icon">💡</div>
            <div class="pill-val">Nocturna</div>
            <div class="pill-label">Iluminación</div>
          </div>
          <div class="info-pill">
            <div class="pill-icon">🚿</div>
            <div class="pill-val">Sí</div>
            <div class="pill-label">Vestuarios</div>
          </div>
          <div class="info-pill">
            <div class="pill-icon">💰</div>
            <div class="pill-val">$60k</div>
            <div class="pill-label">Por hora</div>
          </div>
        </div>

        <!-- CALENDARIO -->
        <div class="section-header"><h3>📅 Elige tu fecha</h3></div>
        <div class="cal-container">
          <div class="cal-top">
            <button class="cal-nav-btn">‹</button>
            <h3>Noviembre 2025</h3>
            <button class="cal-nav-btn">›</button>
          </div>
          <div class="cal-body">
            <div class="cal-days-row">
              <div class="cal-day-name">D</div><div class="cal-day-name">L</div>
              <div class="cal-day-name">M</div><div class="cal-day-name">X</div>
              <div class="cal-day-name">J</div><div class="cal-day-name">V</div>
              <div class="cal-day-name">S</div>
            </div>
            <div class="cal-dates-grid">
              <div class="cal-date empty"></div>
              <div class="cal-date empty"></div>
              <div class="cal-date empty"></div>
              <div class="cal-date empty"></div>
              <div class="cal-date past">1</div>
              <div class="cal-date past">2</div>
              <div class="cal-date past">3</div>
              <div class="cal-date past">4</div>
              <div class="cal-date past">5</div>
              <div class="cal-date past">6</div>
              <div class="cal-date past">7</div>
              <div class="cal-date past">8</div>
              <div class="cal-date selected hoy">9<div class="mini-dot"></div></div>
              <div class="cal-date disponible">10<div class="mini-dot"></div></div>
              <div class="cal-date disponible">11<div class="mini-dot"></div></div>
              <div class="cal-date disponible">12<div class="mini-dot"></div></div>
              <div class="cal-date poco">13<div class="mini-dot"></div></div>
              <div class="cal-date ocupado">14</div>
              <div class="cal-date disponible">15<div class="mini-dot"></div></div>
              <div class="cal-date disponible">16<div class="mini-dot"></div></div>
              <div class="cal-date disponible">17<div class="mini-dot"></div></div>
              <div class="cal-date poco">18<div class="mini-dot"></div></div>
              <div class="cal-date disponible">19<div class="mini-dot"></div></div>
              <div class="cal-date ocupado">20</div>
              <div class="cal-date ocupado">21</div>
              <div class="cal-date disponible">22<div class="mini-dot"></div></div>
              <div class="cal-date disponible">23<div class="mini-dot"></div></div>
              <div class="cal-date disponible">24<div class="mini-dot"></div></div>
              <div class="cal-date poco">25<div class="mini-dot"></div></div>
              <div class="cal-date disponible">26<div class="mini-dot"></div></div>
              <div class="cal-date ocupado">27</div>
              <div class="cal-date disponible">28<div class="mini-dot"></div></div>
              <div class="cal-date disponible">29<div class="mini-dot"></div></div>
              <div class="cal-date disponible">30<div class="mini-dot"></div></div>
            </div>
          </div>
          <div class="cal-legend">
            <div class="legend-item"><div class="legend-dot" style="background:var(--verde-light);border:1px solid #A5D6A7;"></div><span>Disponible</span></div>
            <div class="legend-item"><div class="legend-dot" style="background:var(--amarillo-light);border:1px solid #FFE082;"></div><span>Pocos horarios</span></div>
            <div class="legend-item"><div class="legend-dot" style="background:var(--rojo-light);border:1px solid #FFCDD2;"></div><span>Ocupado</span></div>
          </div>
        </div>

        <!-- HORARIOS -->
        <div class="section-header"><h3>🕐 Elige tu horario</h3></div>
        <div class="horarios-container">
          <div class="horarios-grid">
            <div class="hora-slot ocupado"><div class="h-time">6:00 AM</div><div class="h-label">1 hora</div><div class="h-price" style="color:var(--rojo);">Ocupado</div></div>
            <div class="hora-slot ocupado"><div class="h-time">7:00 AM</div><div class="h-label">1 hora</div><div class="h-price" style="color:var(--rojo);">Ocupado</div></div>
            <div class="hora-slot poco"><div class="h-time">8:00 AM</div><div class="h-label">1 hora</div><div class="h-price" style="color:var(--amarillo);">Último</div></div>
            <div class="hora-slot libre selected"><div class="h-time" style="color:#fff;">10:00 AM</div><div class="h-label" style="color:rgba(255,255,255,0.7);">1 hora</div><div class="h-price" style="color:rgba(255,255,255,0.8);">$60.000</div></div>
            <div class="hora-slot libre"><div class="h-time">11:00 AM</div><div class="h-label">1 hora</div><div class="h-price">$60.000</div></div>
            <div class="hora-slot libre"><div class="h-time">12:00 PM</div><div class="h-label">1 hora</div><div class="h-price">$60.000</div></div>
            <div class="hora-slot libre"><div class="h-time">2:00 PM</div><div class="h-label">1 hora</div><div class="h-price">$60.000</div></div>
            <div class="hora-slot ocupado"><div class="h-time">3:00 PM</div><div class="h-label">1 hora</div><div class="h-price" style="color:var(--rojo);">Ocupado</div></div>
            <div class="hora-slot libre"><div class="h-time">5:00 PM</div><div class="h-label">1 hora</div><div class="h-price">$60.000</div></div>
          </div>
        </div>

        <button class="btn-main">Continuar → Confirmar datos</button>
        <div class="spacer"></div>
      </div>
      <div class="bottom-nav">
        <div class="nav-item"><div class="nav-icon">🏠</div><div class="nav-text">Inicio</div></div>
        <div class="nav-item"><div class="nav-icon active">📅</div><div class="nav-text active">Reservas</div><div class="nav-dot"></div></div>
        <div class="nav-item"><div class="nav-icon">🗺️</div><div class="nav-text">Mapa</div></div>
        <div class="nav-item"><div class="nav-icon">👤</div><div class="nav-text">Perfil</div></div>
      </div>
    </div>
  </div>

  <!-- ============ PANTALLA 3: FORMULARIO + PAGO ============ -->
  <div class="device-col">
    <div class="device-label">3. Confirmar Datos y Pago</div>
    <div class="phone">
      <div class="notch"></div>
      <div class="status-bar"><span class="time">9:46</span><div class="icons"><span>📶</span><span>WiFi</span><span>🔋</span></div></div>
      <div class="app-bar">
        <div class="back-btn">←</div>
        <div style="flex:1;"><div class="title" style="font-size:17px;">Confirmar reserva</div></div>
      </div>

      <!-- STEPS -->
      <div class="progress-bar">
        <div class="step-item done">
          <div class="step-circle">✓</div>
          <div class="step-label">Cancha</div>
        </div>
        <div class="step-item done">
          <div class="step-circle">✓</div>
          <div class="step-label">Fecha</div>
        </div>
        <div class="step-item active">
          <div class="step-circle">3</div>
          <div class="step-label">Datos</div>
        </div>
        <div class="step-item">
          <div class="step-circle">4</div>
          <div class="step-label">Pago</div>
        </div>
      </div>

      <div class="screen">
        <!-- RESUMEN PREVIO -->
        <div style="background:var(--verde-light);border:1.5px solid var(--verde-mid);border-radius:12px;margin:14px 18px 0;padding:12px 14px;display:flex;align-items:center;gap:12px;">
          <div style="font-size:28px;">⚽</div>
          <div style="flex:1;">
            <div style="font-size:14px;font-weight:700;color:var(--verde);">Cancha El Bosque</div>
            <div style="font-size:12px;color:var(--texto2);">Sáb. 9 nov · 10:00–11:00 AM</div>
          </div>
          <div style="font-size:16px;font-weight:800;color:var(--verde);">$60k</div>
        </div>

        <!-- FORMULARIO -->
        <div class="form-container" style="margin-top:14px;">
          <div class="form-card">
            <div class="form-card-header">👤 Datos del jugador</div>
            <div class="form-body">
              <div class="form-group">
                <label>Nombre completo</label>
                <div class="input-with-icon">
                  <span class="input-icon">👤</span>
                  <input type="text" class="form-input" placeholder="Ej. Carlos Martínez" value="Carlos Martínez" readonly>
                </div>
              </div>
              <div class="form-row">
                <div class="form-group">
                  <label>Celular</label>
                  <div class="input-with-icon">
                    <span class="input-icon">📱</span>
                    <input type="text" class="form-input" placeholder="3XX..." value="312-456-7890" readonly>
                  </div>
                </div>
                <div class="form-group">
                  <label>Jugadores</label>
                  <input type="text" class="form-input" value="10 jugadores" readonly>
                </div>
              </div>
              <div class="form-group">
                <label>Email (opcional)</label>
                <div class="input-with-icon">
                  <span class="input-icon">✉️</span>
                  <input type="text" class="form-input" placeholder="tu@email.com" value="carlos@email.com" readonly>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- MÉTODOS DE PAGO -->
        <div class="form-container">
          <div class="form-card">
            <div class="form-card-header">💳 Método de pago</div>
            <div class="form-body">
              <div class="pago-opciones">
                <div class="pago-opcion selected">
                  <div class="pago-icon">🏦</div>
                  <div class="pago-info">
                    <div class="pago-nombre">PSE – Débito bancario</div>
                    <div class="pago-desc">Pago inmediato desde tu banco</div>
                  </div>
                  <div class="radio-circle"><div class="radio-dot"></div></div>
                </div>
                <div class="pago-opcion">
                  <div class="pago-icon">💚</div>
                  <div class="pago-info">
                    <div class="pago-nombre">Nequi</div>
                    <div class="pago-desc">Transferencia digital instantánea</div>
                  </div>
                  <div class="radio-circle"></div>
                </div>
                <div class="pago-opcion">
                  <div class="pago-icon">🟡</div>
                  <div class="pago-info">
                    <div class="pago-nombre">Daviplata</div>
                    <div class="pago-desc">Billetera digital Davivienda</div>
                  </div>
                  <div class="radio-circle"></div>
                </div>
                <div class="pago-opcion">
                  <div class="pago-icon">💵</div>
                  <div class="pago-info">
                    <div class="pago-nombre">Efectivo (en cancha)</div>
                    <div class="pago-desc">Paga al llegar. Reserva sin garantía.</div>
                  </div>
                  <div class="radio-circle"></div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- RESUMEN FINAL -->
        <div class="resumen-hf">
          <div class="resumen-header">📋 Resumen de tu reserva</div>
          <div class="resumen-body">
            <div class="resumen-row"><span class="r-label">⚽ Cancha</span><span class="r-val">El Bosque</span></div>
            <div class="resumen-row"><span class="r-label">📅 Fecha</span><span class="r-val">Sáb. 9 nov 2025</span></div>
            <div class="resumen-row"><span class="r-label">🕐 Horario</span><span class="r-val">10:00 – 11:00 AM</span></div>
            <div class="resumen-row"><span class="r-label">👥 Jugadores</span><span class="r-val">10 jugadores</span></div>
            <div class="resumen-row"><span class="r-label">💳 Pago</span><span class="r-val pago-tag">PSE ✓</span></div>
            <div class="resumen-row"><span class="r-label" style="font-weight:700;">💰 Total</span><span class="r-val price">$60.000</span></div>
          </div>
        </div>

        <button class="btn-main">🔒 Confirmar y pagar $60.000</button>
        <div style="text-align:center;font-size:11px;color:var(--texto2);margin:-4px 18px 14px;line-height:1.5;">
          Al confirmar aceptas los <span style="color:var(--verde);font-weight:600;">términos y condiciones</span>.<br>Cancelación gratuita hasta 2h antes del partido.
        </div>
        <div class="spacer"></div>
      </div>
      <div class="bottom-nav">
        <div class="nav-item"><div class="nav-icon">🏠</div><div class="nav-text">Inicio</div></div>
        <div class="nav-item"><div class="nav-icon active">📅</div><div class="nav-text active">Reservas</div><div class="nav-dot"></div></div>
        <div class="nav-item"><div class="nav-icon">🗺️</div><div class="nav-text">Mapa</div></div>
        <div class="nav-item"><div class="nav-icon">👤</div><div class="nav-text">Perfil</div></div>
      </div>
    </div>
  </div>

  <!-- ============ PANTALLA 4: CONFIRMACIÓN ============ -->
  <div class="device-col">
    <div class="device-label">4. Confirmación Exitosa</div>
    <div class="phone">
      <div class="notch"></div>
      <div class="status-bar"><span class="time">9:48</span><div class="icons"><span>📶</span><span>WiFi</span><span>🔋</span></div></div>
      <div class="app-bar">
        <div class="title" style="font-size:17px;">Reserva confirmada</div>
      </div>
      <div class="screen">
        <div class="confirm-screen">
          <div class="confirm-anim">✅</div>
          <div class="confirm-title">¡Tu cancha está lista!</div>
          <div class="confirm-sub">Recibirás la confirmación por<br>WhatsApp y correo electrónico.</div>

          <div class="codigo-box-hf">
            <div class="codigo-label">Código de reserva</div>
            <div class="codigo-val">FC-2847</div>
          </div>

          <div class="resumen-hf" style="margin:0 0 14px; width:100%;">
            <div class="resumen-header">📋 Detalles de tu reserva</div>
            <div class="resumen-body">
              <div class="resumen-row"><span class="r-label">⚽ Cancha</span><span class="r-val">El Bosque</span></div>
              <div class="resumen-row"><span class="r-label">📅 Fecha</span><span class="r-val">Sáb. 9 nov</span></div>
              <div class="resumen-row"><span class="r-label">🕐 Hora</span><span class="r-val">10:00 – 11:00 AM</span></div>
              <div class="resumen-row"><span class="r-label">👤 Jugador</span><span class="r-val">Carlos Martínez</span></div>
              <div class="resumen-row"><span class="r-label">💳 Pago</span><span class="r-val pago-tag">PSE confirmado ✓</span></div>
              <div class="resumen-row"><span class="r-label" style="font-weight:700;">💰 Total</span><span class="r-val price">$60.000</span></div>
            </div>
          </div>

          <div class="share-btns">
            <div class="share-btn"><span>💬</span>WhatsApp</div>
            <div class="share-btn"><span>📲</span>Compartir</div>
            <div class="share-btn"><span>🗓️</span>Calendario</div>
          </div>

          <button class="btn-main" style="width:100%;margin:0 0 10px;">Ver mis reservas</button>
          <button class="btn-secondary-hf" style="width:100%;margin:0 0 10px;">Reservar otra cancha</button>
          <div class="cancel-note">¿Necesitas cancelar? Tienes hasta las <strong>8:00 AM</strong> del mismo día sin costo adicional.</div>
        </div>
      </div>
      <div class="bottom-nav">
        <div class="nav-item"><div class="nav-icon">🏠</div><div class="nav-text">Inicio</div></div>
        <div class="nav-item"><div class="nav-icon active">📅</div><div class="nav-text active">Reservas</div><div class="nav-dot"></div></div>
        <div class="nav-item"><div class="nav-icon">🗺️</div><div class="nav-text">Mapa</div></div>
        <div class="nav-item"><div class="nav-icon">👤</div><div class="nav-text">Perfil</div></div>
      </div>
    </div>
  </div>

  <!-- ============ PANTALLA 5: PANEL ADMIN ============ -->
  <div class="device-col">
    <div class="device-label">5. Panel Administrador</div>
    <div class="phone">
      <div class="notch"></div>
      <div class="status-bar"><span class="time">9:41</span><div class="icons"><span>📶</span><span>WiFi</span><span>🔋</span></div></div>
      <div class="screen" style="flex:1;">
        <!-- ADMIN HEADER -->
        <div class="admin-header">
          <div class="admin-welcome">Panel de gestión</div>
          <div class="admin-name">El Bosque ⚽</div>
          <div class="stats-row">
            <div class="stat-card">
              <div class="stat-num">8</div>
              <div class="stat-label">Reservas hoy</div>
            </div>
            <div class="stat-card">
              <div class="stat-num">3</div>
              <div class="stat-label">Disponibles</div>
            </div>
            <div class="stat-card">
              <div class="stat-num">$480k</div>
              <div class="stat-label">Ingresos día</div>
            </div>
          </div>
        </div>

        <!-- CHIPS ADMIN -->
        <div class="chips-row" style="background:#fff;border-bottom:1px solid var(--gris2);">
          <div class="chip active">Hoy</div>
          <div class="chip">Esta semana</div>
          <div class="chip">Este mes</div>
        </div>

        <!-- AGENDA -->
        <div class="agenda-section">
          <h3>📋 Agenda del día <span style="font-size:12px;color:var(--texto2);font-weight:400;">Sáb. 9 nov</span></h3>

          <div class="reserva-item-hf">
            <div class="hora-badge"><div class="h">6</div><div class="m">AM</div></div>
            <div class="reserva-info-hf">
              <div class="r-nombre">Carlos Martínez</div>
              <div class="r-detalle">👥 10 jugadores · 🏦 PSE pagado</div>
            </div>
            <span class="status-badge confirmada">✓ Confirmada</span>
          </div>

          <div class="reserva-item-hf">
            <div class="hora-badge"><div class="h">7</div><div class="m">AM</div></div>
            <div class="reserva-info-hf">
              <div class="r-nombre">Liga Barrio Norte</div>
              <div class="r-detalle">👥 14 jugadores · 🏦 PSE pagado</div>
            </div>
            <span class="status-badge confirmada">✓ Confirmada</span>
          </div>

          <div class="reserva-item-hf" style="border-color:var(--amarillo-light);">
            <div class="hora-badge" style="background:var(--amarillo-light);"><div class="h" style="color:var(--amarillo);">8</div><div class="m">AM</div></div>
            <div class="reserva-info-hf">
              <div class="r-nombre">Andrés Gómez</div>
              <div class="r-detalle">👥 10 jugadores · ⏳ Pago pendiente</div>
            </div>
            <span class="status-badge pendiente">⚠ Pendiente</span>
          </div>

          <div class="reserva-item-hf">
            <div class="hora-badge"><div class="h">10</div><div class="m">AM</div></div>
            <div class="reserva-info-hf">
              <div class="r-nombre">Juan Sebastián Rojas</div>
              <div class="r-detalle">👥 10 jugadores · 💚 Nequi pagado</div>
            </div>
            <span class="status-badge confirmada">✓ Confirmada</span>
          </div>

          <div class="reserva-item-hf" style="border-style:dashed;background:var(--gris1);">
            <div class="hora-badge" style="background:var(--gris2);"><div class="h" style="color:#aaa;">11</div><div class="m">AM</div></div>
            <div class="reserva-info-hf">
              <div class="r-nombre" style="color:#aaa;">Sin reserva</div>
              <div class="r-detalle">Horario libre</div>
            </div>
            <span class="status-badge libre">Libre</span>
          </div>

          <div class="reserva-item-hf">
            <div class="hora-badge"><div class="h">2</div><div class="m">PM</div></div>
            <div class="reserva-info-hf">
              <div class="r-nombre">Torneos Cauca FC</div>
              <div class="r-detalle">👥 20 jugadores · 🏦 PSE pagado</div>
            </div>
            <span class="status-badge confirmada">✓ Confirmada</span>
          </div>
        </div>

        <button class="btn-main" style="margin-top:4px;">+ Bloquear / Agregar horario</button>
        <div class="spacer"></div>
      </div>
      <div class="bottom-nav">
        <div class="nav-item"><div class="nav-icon active">📋</div><div class="nav-text active">Agenda</div><div class="nav-dot"></div></div>
        <div class="nav-item"><div class="nav-icon">📊</div><div class="nav-text">Reportes</div></div>
        <div class="nav-item"><div class="nav-icon">⚙️</div><div class="nav-text">Config.</div></div>
        <div class="nav-item"><div class="nav-icon">👤</div><div class="nav-text">Perfil</div></div>
      </div>
    </div>
  </div>

  <!-- ============ PANTALLA 6: ENCUESTA DE USABILIDAD ============ -->
  <div class="device-col">
    <div class="device-label">6. Encuesta de Usabilidad</div>
    <div class="phone">
      <div class="notch"></div>
      <div class="status-bar"><span class="time">9:50</span><div class="icons"><span>📶</span><span>WiFi</span><span>🔋</span></div></div>
      <div class="app-bar">
        <div class="back-btn">←</div>
        <div style="flex:1;"><div class="title" style="font-size:16px;">Encuesta rápida</div><div class="subtitle">5 preguntas · ~2 min</div></div>
      </div>
      <div class="screen">
        <div class="encuesta-screen">
          <div style="font-size:12px;color:var(--texto2);margin-bottom:8px;display:flex;justify-content:space-between;">
            <span>Pregunta 3 de 5</span>
            <span style="color:var(--verde);font-weight:600;">60%</span>
          </div>
          <div class="encuesta-progress"><div class="bar" style="width:60%;"></div></div>

          <!-- Q1 (mostrada como completada) -->
          <div class="encuesta-card" style="opacity:0.65;border-color:var(--verde-mid);">
            <div class="q-num">✓ Pregunta 1 – Completada</div>
            <div class="q-text" style="font-size:13px;color:var(--texto2);">¿Con qué frecuencia reservas canchas sintéticas?</div>
            <div style="background:var(--verde-light);border-radius:8px;padding:8px 12px;font-size:13px;color:var(--verde);font-weight:600;">✓ 1–2 veces por semana</div>
          </div>

          <!-- Q2 (mostrada como completada) -->
          <div class="encuesta-card" style="opacity:0.65;border-color:var(--verde-mid);">
            <div class="q-num">✓ Pregunta 2 – Completada</div>
            <div class="q-text" style="font-size:13px;color:var(--texto2);">¿Cómo reservas actualmente?</div>
            <div style="background:var(--verde-light);border-radius:8px;padding:8px 12px;font-size:13px;color:var(--verde);font-weight:600;">✓ WhatsApp al administrador</div>
          </div>

          <!-- Q3 activa -->
          <div class="encuesta-card" style="border-color:var(--verde);box-shadow:0 0 0 2px var(--verde-mid);">
            <div class="q-num">📌 Pregunta 3 – Actual</div>
            <div class="q-text">¿Qué tan fácil te resultó encontrar una cancha disponible en FutCancha?</div>
            <div class="q-options">
              <div class="q-option">
                <div class="opt-radio"></div>
                Muy fácil – encontré lo que necesitaba al instante
              </div>
              <div class="q-option selected">
                <div class="opt-radio"><div class="opt-dot"></div></div>
                Fácil – tardé 1–2 pasos, pero fue claro
              </div>
              <div class="q-option">
                <div class="opt-radio"></div>
                Regular – tuve alguna duda en el proceso
              </div>
              <div class="q-option">
                <div class="opt-radio"></div>
                Difícil – no entendí bien cómo usarlo
              </div>
            </div>
          </div>

          <button class="btn-main" style="margin:0 0 8px;">Siguiente pregunta →</button>
          <div style="text-align:center;font-size:11px;color:var(--gris3);">Tus respuestas nos ayudan a mejorar FutCancha</div>
          <div class="spacer"></div>
        </div>
      </div>
      <div class="bottom-nav">
        <div class="nav-item"><div class="nav-icon">🏠</div><div class="nav-text">Inicio</div></div>
        <div class="nav-item"><div class="nav-icon active">📋</div><div class="nav-text active">Encuesta</div><div class="nav-dot"></div></div>
        <div class="nav-item"><div class="nav-icon">🗺️</div><div class="nav-text">Mapa</div></div>
        <div class="nav-item"><div class="nav-icon">👤</div><div class="nav-text">Perfil</div></div>
      </div>
    </div>
  </div>

</div><!-- /device-grid -->

<!-- FLOW OVERVIEW -->
<div class="flow-overview">
  <h2>🔄 Flujo de usuario representado (alta fidelidad)</h2>
  <div class="flow-steps">
    <div class="flow-step active">1. 🏠 Buscar cancha</div>
    <div class="flow-arrow">→</div>
    <div class="flow-step">2. 📅 Ver disponibilidad</div>
    <div class="flow-arrow">→</div>
    <div class="flow-step">3. 🕐 Elegir horario</div>
    <div class="flow-arrow">→</div>
    <div class="flow-step">4. 👤 Confirmar datos</div>
    <div class="flow-arrow">→</div>
    <div class="flow-step">5. 💳 Pagar</div>
    <div class="flow-arrow">→</div>
    <div class="flow-step">6. ✅ ¡Reserva lista!</div>
  </div>
  <div class="flow-meta">
    Prototipo de alta fidelidad – IHC Tercer Corte · Unicomfacauca 2025 · Juan Sebastián Rojas Bravo · Juan Camilo Solarte Trochez
  </div>
</div>

</body>
</html>
