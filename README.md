# DeepSeek Horarios Peak & Off-Peak Tracker — OpenCode Go

Este proyecto proporciona un visualizador interactivo y dashboard web para consultar los horarios de alta demanda (**Peak**) y demanda reducida (**Off-Peak**) de los modelos **DeepSeek** en el servicio **OpenCode Go**.

---

## 🚀 Cómo Usarlo

Simplemente abre el archivo [`index.html`](file:///C:/Users/meliodaslosven/Desktop/Projects/deepseek-horarios/index.html) en cualquier navegador web (Chrome, Edge, Firefox, Safari):

- Puedes hacer doble clic sobre `index.html` en el explorador de archivos.
- O ejecutar en PowerShell / terminal:
  ```powershell
  Start-Process "index.html"
  ```

---

## 🕒 Regla Oficial de Horarios (OpenCode Go)

| Horario | Días aplicables | Horas Oficiales (UTC) | Tarifa de Tokens |
| :--- | :--- | :--- | :--- |
| 🔴 **Peak** (Alta demanda) | Lunes a Viernes | **01:00 - 04:00 UTC** y **06:00 - 10:00 UTC** (7h/día) | Tarifa estándar |
| 🟢 **Off-Peak** (Demanda baja) | Lunes a Viernes | **00:00 - 01:00**, **04:00 - 06:00**, **10:00 - 24:00 UTC** (17h/día) | **50% de descuento directo** |
| 🟢 **Off-Peak Fin de Semana** | Sábado y Domingo | **Todo el día (00:00 - 24:00 UTC)** | **50% de descuento directo** |

---

## 💰 Comparativa de Tarifas (por 1M Tokens)

Precios idénticos para **Go** ($10/mes) y **Go Plus** ($40/mes):

| Modelo | Estado | Entrada (1M) | Salida (1M) | Lectura Caché (1M) | Límite mensual |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **DeepSeek V4.1 Flash** | 🟢 Off-Peak<br>🔴 Peak | $0.15<br>$0.30 | $0.60<br>$1.20 | $0.003<br>$0.006 | $60 USD |
| **DeepSeek V4 Pro** | 🟢 Off-Peak<br>🔴 Peak | $0.66<br>$1.32 | $1.98<br>$3.96 | $0.022<br>$0.044 | $15 USD |
| **DeepSeek V4 Flash** | 🟢 Off-Peak<br>🔴 Peak | $0.15<br>$0.30 | $0.60<br>$1.20 | $0.003<br>$0.006 | $30 USD |
| **DeepSeek V4 Flash Vision Exp** | 🟢 Off-Peak<br>🔴 Peak | $0.15<br>$0.30 | $0.60<br>$1.20 | $0.003<br>$0.006 | $15 USD |

---

## ✨ Características de la Aplicación Web

1. **Reloj de Pared Analógico 24H y Estado en Tiempo Real**:
   - Reloj analógico de pared interactivo con dial circular de 24 horas y sectores sombreados en **verde (Off-Peak 50% OFF)** y **rojo (Peak)**.
   - Agujas horarias (hora, minuto y segundo) sincronizadas en tiempo real que recorren físicamente los sectores del día.
   - Panel de información con hora oficial local (Perú predeterminado), hora UTC y contador regresivo exacto hacia el próximo cambio de horario.

2. **Conversor Inteligente de Zona Horaria**:
   - Detecta tu hora local automáticamente y traduce las franjas UTC a tu horario local (Bogotá/Lima UTC-5, México UTC-6, Madrid UTC+1/+2, Buenos Aires UTC-3, etc.).
   
3. **Línea de Tiempo Diaria (24 Horas) con Selector de Días**:
   - Selector interactivo para consultar **Hoy**, **Mañana**, **Pasado mañana** o cualquiera de los próximos 7 días.
   - Gráfico visual interactivo con bloques verdes (Off-Peak con 50% de descuento) y rojos (Peak).
   - Indicador de hora actual en movimiento para la vista de "Hoy".
   - Cálculo automático de horas Peak/Off-Peak adaptado a las transiciones de fecha y fines de semana según tu zona horaria.

4. **Matriz Semanal**:
   - Calendario de Lunes a Domingo destacando los fines de semana 100% Off-Peak.

5. **Calculadora Interactiva de Costos**:
   - Configura tokens de entrada, salida y caché para simular cuánto ahorras programando en horas Off-Peak.

6. **Guía de Conexión en OpenCode**:
   - Comandos TUI (`/connect`), IDs de modelo (`opencode-go/deepseek-v4.1-flash`) y endpoints oficiales.
