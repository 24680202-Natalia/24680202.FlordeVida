# TecNM Cuautla
# 24680202 Natalia Reyes Baños 4° Semestre Grupo 3 12-Feb-2026
# 🌸 Practica 1 Flor de la Vida en Blender

### 1. Instalar y abrir Blender
*   **Descarga Blender:** Si no lo tienes, bájalo en [blender.org](https://www.blender.org).
  <img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/8fe9ae97-a89b-45b3-8097-99914321cfe4" />

*   **Abre el entorno:** Inicia Blender y haz clic en la pestaña **Scripting** en el menú superior.
*   **Nuevo Script:** Haz clic en el botón **+ New** para abrir un editor de texto vacío.
  <img width="1890" height="902" alt="image" src="https://github.com/user-attachments/assets/e8ffecad-3a0d-464b-ae05-38749a1b0e7d" />


### 2. El Código (Automatizado con Bucle)
Copia y pega el siguiente código en el editor de Blender. Este script utiliza un ciclo para calcular las posiciones matemáticas de cada círculo sin tener que repetir líneas de código.

```python
import bpy
import math

# 1. Limpiar la escena (Borra objetos anteriores)
bpy.ops.object.select_all(action='SELECT')
bpy.ops.object.delete()

# 2. Parámetros de la figura
radio = 3
angulo_actual = 0
paso_angular = 60 # 60 grados para obtener 6 círculos exactos alrededor

# 3. Crear Círculo Central
bpy.ops.mesh.primitive_circle_add(radius=radio, location=(0, 0, 0), vertices=64)

# 4. INICIO DEL PATRÓN REPETITIVO (Bucle While)
# Mientras el ángulo no complete los 360 grados, el script seguirá creando círculos
while angulo_actual < 360:
    # Convertir coordenadas polares a cartesianas (x, y)
    x = radio * math.cos(math.radians(angulo_actual))
    y = radio * math.sin(math.radians(angulo_actual))
    
    # Crear el círculo periférico en la posición calculada
    bpy.ops.mesh.primitive_circle_add(radius=radio, location=(x, y, 0), vertices=64)
    
    # Aumentar el ángulo para la siguiente posición
    angulo_actual += paso_angular
```
### 3. Resultado final
Por último la flor debió de quedar de la siguiente manera
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/8674b757-ec28-4c08-9045-386dd3cd31e0" />

