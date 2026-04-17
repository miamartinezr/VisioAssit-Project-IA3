# VisioAssist

Sistema de asistencia a la navegación para personas con discapacidad visual basado en inteligencia artificial, diseñado para entornos urbanos como Sucre, Bolivia.

---

## Descripción

**VisioAssist** es un prototipo que utiliza visión por computadora en un smartphone Android para detectar obstáculos a nivel de torso y cabeza en tiempo real.

El sistema combina:

* Detección de objetos (**YOLOv8n**)
* Estimación de profundidad (**Depth Anything V2**)

Genera **alertas de voz** que informan al usuario sobre:

* Tipo de obstáculo
* Dirección
* Proximidad

---

## Problema

Las personas con discapacidad visual enfrentan dificultades para detectar obstáculos elevados (letreros, ramas, toldos), ya que el bastón blanco solo cubre el nivel del suelo.

En ciudades como Sucre, este problema se agrava por:

* Infraestructura histórica sin accesibilidad
* Falta de soluciones tecnológicas accesibles
* Alto costo de dispositivos comerciales

---

## Solución

VisioAssist propone un sistema:

*  Basado en smartphone (bajo costo)
*  Con inteligencia artificial en tiempo real
*  Con retroalimentación auditiva
*  Adaptado al entorno urbano local

---

## Tecnologías utilizadas

* **YOLOv8n** → detección de objetos
* **Depth Anything V2** → estimación de profundidad
* **Python / PyTorch** → entrenamiento
* **OpenCV** → procesamiento de imágenes
* **Roboflow** → anotación del dataset
* **Android (TTS)** → síntesis de voz

---

## Dataset

*  Imágenes capturadas en Sucre (centro histórico)
*  1,551 instancias anotadas
*  6 clases:

  * person
  * pole
  * sign
  * awning
  * tree trunk
  * branch

Clases con menor representación:

* branch (crítica)
* awning (mejorable)

---

## Resultados del modelo

**Test (evaluación real):**

* mAP@50: **84.2%**
* Precisión: **82.5%**
* Recall: **76.1%**

Buen desempeño general
Mejora necesaria en detección de ramas

---

## Arquitectura del sistema

Pipeline:

1. Captura de imagen (cámara del smartphone)
2. Detección de objetos (YOLOv8n)
3. Estimación de profundidad (Depth Anything V2)
4. Fusión de resultados
5. Generación de alertas de voz

---

## Implementación

* Dispositivo: **Samsung S23+**
* Ejecución en tiempo real: **~15 FPS**
* Procesamiento local (Edge AI)
* Uso de auriculares Bluetooth

---

## Limitaciones

* Dependencia de luz diurna
* Bajo rendimiento en clase "branch"
* Dataset limitado
* No reemplaza el bastón blanco

---

## Trabajo futuro

* Ampliar dataset (especialmente ramas)
* Mejorar recall del modelo
* Optimizar rendimiento en móviles
* Implementar app Android nativa
* Pruebas con usuarios reales

---

## Consideraciones éticas

*  Procesamiento local (sin nube)
*  Sin recolección de datos personales
*  Enfoque inclusivo
*  Solución de bajo costo

---

## Impacto

* Mejora la autonomía de personas con discapacidad visual
* Promueve accesibilidad en ciudades históricas
* Demuestra viabilidad de IA en Bolivia

---

## Autor

Milton Rodriguez

---

## Licencia

Este proyecto será liberado como código abierto para fines académicos e investigación.
