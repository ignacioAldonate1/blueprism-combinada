# Automatización de Operaciones Matemáticas con Blue Prism

Este proyecto es una automatización desarrollada en **Blue Prism** como parte de un ejercicio práctico.  
El proceso consiste en abrir una aplicación de escritorio llamada `combinada.exe`, que genera operaciones matemáticas aleatorias (como sumas, restas, multiplicaciones y divisiones). El robot debe:

1. Leer cada operación generada por la aplicación.
2. Calcular el resultado correspondiente.
3. Ingresar ese resultado en la interfaz del programa.
4. Registrar cada operación en una **Queue** de Blue Prism, marcando si fue exitosa o fallida.
5. Finalmente, generar un **reporte en Excel** con el detalle de todas las operaciones realizadas.

Además, el proceso está diseñado para manejar errores como divisiones por cero, asegurar un diseño limpio y controlado, y registrar todas las excepciones.

---

## 🛠️ Funcionalidades del Proceso

- **Verificación y ejecución de aplicación externa**
  - Comprueba si `combinada.exe` se encuentra en la ruta `C:\blueprism\combinada`.
  - Si no está presente, lanza una excepción controlada.

- **Carga y resolución de operaciones**
  - Ejecuta la aplicación y presiona el botón "Cargar datos".
  - Espera dinámicamente hasta que se generen operaciones (cantidad aleatoria).
  - Resuelve cada operación matemática y carga el resultado en la aplicación.

- **Manejo de excepciones**
  - Detecta operaciones inválidas (como divisiones por cero).
  - Marca esos casos como excepciones y continúa con el resto del proceso.

- **Gestión de Queue**
  - Crea un ítem por cada operación en la Queue “combinada”.
  - Taguea cada ítem según el tipo de operación:
    - Suma → `Suma`
    - Resta → `Resta`
    - Multiplicación → `Multiplicacion`
    - División → `Division`

- **Generación de reporte en Excel**
  - Al finalizar, genera un archivo Excel en la misma carpeta que la aplicación.
  - El archivo contiene tres hojas:
    - `Completados`: operaciones exitosas.
    - `Excepciones`: operaciones fallidas.
    - `Items TAGS`: operaciones tagueadas como Suma o División.

---

## ✔️ Buenas prácticas implementadas

- Uso de **templates** y nomenclatura clara en procesos y objetos.
- Separación lógica por páginas y uso de **anchors** para un diseño limpio.
- Descripciones en cada stage y sin nombres genéricos como `Data1`.
- Captura y almacenamiento de excepciones en data items.
- Uso de **variables de ambiente** (sin valores hardcodeados).
- Publicación del proceso en **Control Room**.
- Manejo de ítems pendientes para evitar que queden colgados tras fallos.
- Empaquetado del release con todo el contenido necesario.
