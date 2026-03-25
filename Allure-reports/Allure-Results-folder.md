Versión corregida (lista para copiar)
# 🚨 Allure Results Folder Issue

## 🧪 Problema

La carpeta:

```bash
allure-results

👉 se está generando en la raíz del proyecto (fuera de target).

🧠 💥 ¿Por qué es un problema?

Porque cuando ejecutas:

allure serve target/allure-results

👉 Allure está buscando aquí:

target/allure-results ❌ (vacío o no existe)

Pero tus resultados están aquí:

/allure-results ✅

👉 Resultado:
El reporte muestra 0 tests.

✅ 🔥 Soluciones (elige una)
🥇 Opción 1 (Recomendada) → Corregir ruta

Crea este archivo:

src/test/resources/allure.properties

Y agrega:

allure.results.directory=target/allure-results

👉 Esto obliga a Allure a guardar los resultados en la ruta correcta.

🥈 Opción 2 (Rápida)

Ejecuta:

allure serve allure-results

👉 Apunta directamente a la carpeta real.

🥉 Opción 3 (Debug)

Mueve manualmente la carpeta:

mv allure-results target/
🎯 Conclusión

👉 El problema no es Allure, sino la ruta donde se generan los resultados.
👉 Configurar correctamente allure.results.directory evita este tipo de errores.