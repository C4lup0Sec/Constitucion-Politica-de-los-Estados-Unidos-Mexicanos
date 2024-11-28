---
layout: default
title: Inicio
---
# Constitución Mexicana: Panel Interactivo

Bienvenido a este sitio donde puedes explorar y analizar la Constitución Mexicana.  

- [Descarga en TXT](./Formatos/constitucion.txt)
- [Descarga en JSON](./Formatos/constitucion.json)
- [Ver Scripts](./Scripts)

## Tabla de Contenido

1. Introducción
2. Herramientas utilizadas
3. Visualizaciones interactivas



---

### **2. Ejemplo para el sitio en GitHub Pages**
Vamos a crear un sitio básico en **HTML**, con un panel interactivo inicial.

#### **Archivo `index.html`:**
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Constitución Mexicana</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
</head>
<body>
    <div class="container mt-5">
        <h1 class="text-center">Constitución Mexicana: Panel Interactivo</h1>
        <p class="text-center">Explora, analiza y descarga la Constitución Mexicana en diferentes formatos.</p>

        <div class="row">
            <div class="col-md-4">
                <h3>Descargas</h3>
                <ul>
                    <li><a href="./Formatos/constitucion.txt" download>Texto plano (TXT)</a></li>
                    <li><a href="./Formatos/constitucion.json" download>JSON</a></li>
                    <li><a href="./Formatos/constitucion.md" download>Markdown</a></li>
                </ul>
            </div>
            <div class="col-md-8">
                <h3>Análisis Interactivo</h3>
                <canvas id="wordCloud" width="400" height="200"></canvas>
            </div>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        const ctx = document.getElementById('wordCloud').getContext('2d');
        const chart = new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ['Artículo 1', 'Artículo 2', 'Artículo 3', 'Artículo 4'],
                datasets: [{
                    label: 'Frecuencia de palabras',
                    data: [12, 19, 3, 5],
                    backgroundColor: ['rgba(75, 192, 192, 0.2)'],
                    borderColor: ['rgba(75, 192, 192, 1)'],
                    borderWidth: 1
                }]
            },
            options: {
                responsive: true,
                scales: {
                    y: {
                        beginAtZero: true
                    }
                }
            }
        });
    </script>
</body>
</html>
