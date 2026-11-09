# GCP en Finanzas — Cartera de 4 activos

**Desafío académico de Métodos Numéricos · UMSA · Carrera de Informática**
**Estudiante:** Mario Fabricio Murillo Peñaranda · **Mención:** Inteligencia Artificial y Ciencia de Datos

🔗 **Página web:** `https://TU-USUARIO.github.io/gcp-finanzas/`

## Descripción
Dashboard interactivo que resuelve Ax = b con el **Método de Gradientes Conjugados Precondicionado (GCP)** (Suñagua, 2020) aplicado a una cartera de media-varianza de n = 4 activos (Renta variable, Bonos, Oro, Tecnología/Cripto): A = Σ (covarianzas), b = μ/γ (γ = 3). Compara contra GC simple y contra una solución directa (Cholesky) en tres escenarios: **Ideal, Bajo estrés y Mal condicionado**.

## Contenido de la página
Inicio · Caso de estudio · Formulación (con verificación de simetría y definición positiva) · Entrada de datos · Tres escenarios · Solución de referencia · GCP vs GC · Análisis de errores · Módulo QA · Aporte IA/CD (EDA, covarianzas, sensibilidad) · Conclusiones y referencias.

## Arquitectura
Un único archivo `index.html` (HTML + CSS + JavaScript puro, sin dependencias ni servidor):
- `chol`, `cs`: factorización de Cholesky y solución directa (referencia).
- `eig`: autovalores por rotaciones de Jacobi → κ(A) y κ(M⁻¹A).
- `buildM`: precondicionadores Jacobi y SSOR.
- `pcg`: algoritmo GCP (con M = I equivale a GC simple); criterio ‖r‖₂/‖b‖₂ < 10⁻⁶ y N_máx.
- `validate`: valida simetría y definición positiva sin colapsar.
- `estimate`: limpieza del CSV y estimación de μ y Σ.
- `qa`: las 4 pruebas de software obligatorias.

## Ejecución local
Descargue el repositorio y abra `index.html` en cualquier navegador. No requiere instalación.

## Datos
Retornos mensuales **ilustrativos simulados** (modelo de un factor, semilla fija). Para datos reales, pegue 4 columnas (RV,BS,OR,TC) en el CSV de la sección 10.

## Referencias
- Suñagua S., P. (2020). Método de Gradientes Conjugados Precondicionado. *Revista Boliviana de Matemática*, UMSA, 04, 2–7.
- Golub, G. H., & Van Loan, C. F. (2013). *Matrix Computations* (4th ed.). Johns Hopkins University Press.
- Saad, Y. (2003). *Iterative Methods for Sparse Linear Systems* (2nd ed.). SIAM.
