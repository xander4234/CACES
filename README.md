# Simulador CACES · Enfermería

Simulador de práctica tipo juego para el examen CACES de Enfermería.
Aplicación web estática de un solo archivo (`index.html`), sin dependencias ni proceso de build.

## Contenido
- **509 preguntas** de práctica originales, repartidas en 9 unidades
- **Simulacro general** con el banco completo de preguntas mezcladas
- **Explicaciones por tema**: repasa cada pregunta con su respuesta y explicación
- **Login por nombre** con progreso guardado
- XP, niveles, racha diaria, corazones y ranking de estudiantes
- Mascota guía (cachorro enfermero) con consejos de estudio

## Cómo abrirlo en tu computadora

### Opción A: abrir directo
Haz doble clic en `index.html` y se abrirá en tu navegador.

### Opción B: con Visual Studio Code (recomendado)
1. Abre la carpeta en VS Code: **File → Open Folder → simulador-caces**
2. Instala la extensión **Live Server** (de Ritwick Dey) desde la pestaña de extensiones.
3. Clic derecho sobre `index.html` → **Open with Live Server**.
4. Se abrirá en `http://127.0.0.1:5500` con recarga automática al editar.

## Subir a GitHub

```bash
cd simulador-caces
git init
git add .
git commit -m "Simulador CACES Enfermería"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main
```

## Desplegar en Render

1. Entra a [render.com](https://render.com) e inicia sesión con GitHub.
2. **New + → Static Site** y conecta tu repositorio.
3. Configura:
   - **Build Command:** *(déjalo vacío)*
   - **Publish Directory:** `.`
4. **Create Static Site** → en ~1 minuto tendrás `https://tu-nombre.onrender.com`

### Dominio propio (opcional)
En Render: tu sitio → **Settings → Custom Domains → Add**. Render te dará un
registro **CNAME** que debes agregar en el panel DNS de donde compraste el dominio.
El HTTPS se activa automáticamente.

## Cómo funciona el guardado

La app guarda el login, el progreso, el XP, la racha y el ranking en el
**almacenamiento local del navegador** (`localStorage`). Esto significa:

- ✅ Tu progreso **se conserva** aunque cierres la pestaña o apagues la computadora.
- ✅ Varias personas pueden crear su usuario en el mismo dispositivo y cada una
  mantiene su propio avance; todas aparecen en el ranking.
- ⚠️ El progreso es **por dispositivo y navegador**. Si abres la app en otro
  computador o teléfono, empiezas de cero allí, y el ranking de cada dispositivo
  es independiente.
- ⚠️ Si el usuario borra los datos de navegación del sitio, se pierde el progreso.

Para tener un ranking **global compartido entre todos los usuarios** y que el
progreso siga a la persona en cualquier dispositivo, haría falta agregar un
backend con base de datos (por ejemplo un servicio web en Render + PostgreSQL).

## Estructura

```
simulador-caces/
├── index.html      # La aplicación completa (HTML + CSS + JS)
├── README.md       # Este archivo
└── .gitignore
```

## Nota sobre el contenido

Las preguntas incluidas son material de práctica de elaboración propia, redactado
para repasar temas frecuentes de Enfermería. **No son preguntas oficiales del
examen CACES.** Úsalo como complemento del material oficial de tu institución.
