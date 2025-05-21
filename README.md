# Arnold Cat Map - Encriptación de Imágenes

Este proyecto aplica el **Arnold Cat Map**, una transformación caótica utilizada para cifrar imágenes mediante permutaciones deterministas de sus píxeles.

## ¿Qué hace este código?

- Carga una imagen en escala de grises.
- Muestra la imagen original y su histograma de intensidades.
- Aplica la transformación **Arnold Cat Map** por un número definido de iteraciones.
- Muestra la imagen transformada y su histograma.
- Compara las entropías de la imagen original y la transformada para medir el nivel de aleatoriedad.

##  ¿Qué es el Arnold Cat Map?

Es una transformación matemática definida por:
x' = (x + y) % N
y' = (x + 2y) % N

## 🔧 ¿Qué hace este script?

2. **Muestra la imagen original.**
   - Se usa `matplotlib.pyplot.imshow()` con el mapa de color `'gray'`.

3. **Genera el histograma de la imagen original.**
   - Se grafica con `plt.hist(img.ravel(), bins=256)`.

4. **Aplica el Arnold Cat Map 10 veces.**
   - Cada píxel se reubica usando:
     ```
     x' = (x + y) % N
     y' = (x + 2y) % N
     ```

5. **Muestra la imagen transformada.**
   - Es visualmente más "desordenada", aunque conserva la misma información.

6. **Genera el histograma de la imagen transformada.**

7. **Compara ambas imágenes y sus histogramas en una sola figura 2x2.**

8. **Calcula y muestra la entropía de ambas imágenes.**
   - Se utiliza `scipy.stats.entropy`.

Resultados esperados

### ![image](https://github.com/user-attachments/assets/8026bd34-1786-4337-a1c4-986aac7c568e)
![image](https://github.com/user-attachments/assets/6537c3a9-c9e6-459c-903c-7f4c78c052e3)

- **Imagen original:** Se ve como fue capturada originalmente, en escala de grises.
- **Imagen con Cat Map:** Tiene un patrón más caótico, pero no pierde información (es reversible si se aplica la misma transformación inversa).

Histogramas
- ![image](https://github.com/user-attachments/assets/18b0cdbf-2e31-4949-9eda-4ef0de005812)
- ![image](https://github.com/user-attachments/assets/f206b0ba-a8f9-447c-a224-480342667712)


- Ambos histogramas suelen parecerse, pero si la imagen original tiene muchas repeticiones, el histograma del Cat Map será más uniforme.

Entropía
- ![image](https://github.com/user-attachments/assets/5448bf39-377d-41e0-b3b7-ffbc68f66048)


