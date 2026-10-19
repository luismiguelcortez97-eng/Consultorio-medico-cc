# Consultorio Médico CC

Sistema de gestión para consultorios médicos y servicios de laboratorio.  
Aplicación web 100% client-side (IndexedDB) – lista para GitHub y Render.

---

## Demo local (rápido)

```bash
# Clona o descarga el repositorio
cd ConsultorioMedicoCC
python -m http.server 8080
```

Abre: http://localhost:8080

**Usuario:** `admin`  
**Contraseña:** `cc2024`

| Módulo                | Código   |
|-----------------------|----------|
| Cobros y Laboratorios | `202503` |
| Balance general       | `1973`   |

---

## Subir a GitHub

1. Crea un repositorio nuevo en GitHub (público o privado).
2. En la carpeta del proyecto ejecuta:

```bash
git init
git add .
git commit -m "Consultorio Médico CC - versión inicial"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/ConsultorioMedicoCC.git
git push -u origin main
```

---

## Desplegar en Render (Static Site – recomendado)

### Opción A – Desde el Dashboard (más fácil)

1. Entra a [https://dashboard.render.com](https://dashboard.render.com)
2. **New +** → **Static Site**
3. Conecta tu repositorio de GitHub
4. Configuración:
   - **Name:** `consultorio-medico-cc` (o el que quieras)
   - **Branch:** `main`
   - **Root Directory:** dejar vacío
   - **Build Command:** dejar vacío
   - **Publish Directory:** `.`  (punto)
5. Clic en **Create Static Site**

Render te dará una URL tipo:  
`https://consultorio-medico-cc.onrender.com`

### Opción B – Con Blueprint (`render.yaml`)

El archivo `render.yaml` ya está incluido.  
Al conectar el repositorio, Render puede detectar la configuración automáticamente.

---

## Estructura del proyecto

```
ConsultorioMedicoCC/
├── index.html          ← Punto de entrada
├── css/
│   └── styles.css
├── js/
│   ├── db.js           ← IndexedDB
│   └── app.js          ← Lógica de la aplicación
├── render.yaml         ← Configuración para Render
└── README.md
```

---

## Características

- Login con sesión
- Médicos (alta / edición / baja)
- Pacientes y expedientes
- Consultas clínicas completas + signos vitales obligatorios
- Catálogo de medicamentos + prescripción
- Catálogo de estudios de laboratorio
- Receta médica / Hoja de indicaciones (impresión)
- Cobros del día con auditoría
- Balance general con desglose por médico
- Respaldo y restauración en JSON
- 100% client-side (IndexedDB) – no necesita base de datos en el servidor

---

## Notas importantes

- Los datos se guardan **en el navegador** del usuario (IndexedDB).  
  Cada persona que abra la URL tendrá su propia base de datos local.
- Para uso real en un consultorio se recomienda:
  - Usar siempre el mismo equipo/navegador, **o**
  - Exportar/importar el JSON de respaldo regularmente.
- Los códigos NIP son solo controles de interfaz.
- Esta herramienta **no sustituye** el criterio médico ni es una certificación normativa.

---

**Consultorio Médico CC** · Gracias por confiarnos tu salud.
