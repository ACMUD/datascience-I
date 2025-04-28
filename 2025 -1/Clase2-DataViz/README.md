# Graficos para DS

## Grafica de barras.

Lo usamos cuando queremos comprar la cantidad entre nuestros valores o categorias

### Consejos para hacer buenos gráficos
- Usar un color distinto por cada una de las categorías
- De ser posible, representar las barras de menor a mayor
- Comenzar desde 0 en los ejes.

```python
# Datos
x = ['A', 'B', 'C', 'D']
y = [3, 8, 1, 10]

# Crear la figura y los ejes
fig, ax = plt.subplots()

# Crear la gráfica de barras
ax.bar(x, y)

# Añadir títulos y etiquetas


# Mostrar la gráfica
plt.show()
```

![alt text](img\image.png)


```python
# Crear un DataFrame para ordenar los valores juntos
df = pd.DataFrame({'Categoría': x, 'Valor': y}).sort_values('Valor')

# Crear la figura
fig = go.Figure()

# Añadir la gráfica de barras con diferentes colores
fig.add_trace(go.Bar(
    x=df['Categoría'],
    y=df['Valor'],
    marker_color=['#636EFA', '#EF553B', '#00CC96', '#AB63FA']  # Colores distintos
))

# Añadir título y etiquetas
fig.update_layout(
    title="Gráfica de Barras Ordenada",
    xaxis_title="Categorías",
    yaxis_title="Valores"
)

# Mostrar la gráfica
fig.show()
```
![alt text](img\image2.png)


## Grafica de lineas

Lo usamos cuando queremos mostrar el cambio de una variable (en el eje vertical) a travez de una segunda variable continua(sin cortes) (en el eje horizontal)

### Consejos para hacer buenos graficos
- Usa un intervalo apropiado
- Procurar no poner mas de 5 lineas, y que estas esten separadas
-  EN ALGUNOS CASOS, CORTAR AXIS

![alt text](img\image3.png)
![alt text](img\image4.png)


```python
# Datos
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Crear la figura y los ejes
fig, ax = plt.subplots()

# Crear la gráfica de líneas
ax.plot(x, y)

# Añadir títulos y etiquetas
ax.set_title("Gráfica de Líneas")
ax.set_xlabel("X")
ax.set_ylabel("Y")

# Mostrar la gráfica
plt.show()
```

![alt text](img\image5.png)

```python
# Crear la figura
fig = go.Figure()

# Añadir la gráfica de líneas
fig.add_trace(go.Scatter(x=x, y=y, mode='lines'))

# Añadir título y etiquetas
fig.update_layout(title="Gráfica de Líneas", xaxis_title="X", yaxis_title="Y")

# Mostrar la gráfica
fig.show()
```

![alt text](img\image6.png)