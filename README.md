### Transformaciones sobre la imagen de Lena

Actividad UA3 de Sistemas de percepción en robótica.

En el cuaderno transformaciones_lena.ipynb aplico a la imagen de Lena cinco transformaciones, rotarla, sacar el negativo, umbralizarla, ecualizarla y quitarle el ruido, y comparo los resultados con los histogramas y con algunos valores de los píxeles. La imagen está en la misma carpeta que el cuaderno.

Para ejecutarlo hace falta un entorno de conda con las librerías del requirements.txt:

```
conda create -n vision python=3.13
conda activate vision
pip install -r requirements.txt
```

Luego se abre el cuaderno en VS Code o en Jupyter con el kernel vision y se ejecutan todas las celdas con Run All. Hay que abrirlo desde esta carpeta porque la imagen se carga con ruta relativa. La celda de la rotación hecha a mano tarda unos segundos porque recorre la imagen píxel a píxel.

Lo he probado con Python 3.13, NumPy 2.5.3, OpenCV 5.0.0, Matplotlib 3.11.2 y Seaborn 0.13.2.

Transformaciones que hay en el cuaderno:  
-Rotación con getRotationMatrix2D y warpAffine, y también a mano con la fórmula, de forma directa e inversa  
-Negativo restando a 255, en gris y en color  
-Umbralización con los umbrales 50, 100 y 150 y con el método de Otsu  
-Ecualización con equalizeHist, a mano con el histograma acumulado y en color sobre la Y de YCrCb  
-Eliminación de ruido gaussiano y sal y pimienta con la media, las máscaras entre 10 y entre 16, la mediana y el filtro del bicho raro  

Archivos:  
-transformaciones_lena.ipynb, el cuaderno con el código y los resultados  
-Lena.png, la imagen de Lena en color de 512 x 512  
-requirements.txt, las librerías necesarias, que son numpy, opencv-python, matplotlib, seaborn e ipykernel
