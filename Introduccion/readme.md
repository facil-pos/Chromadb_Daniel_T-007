# Introduccion

## Conocimientos previso

`NOTA: Recomiendo leer la siguiente documentacion sobre pinecone y embeddings`

[Langchain_Documentacion/Pinecone/readme.md at main · facil-pos/Langchain_Documentacion (github.com)](https://github.com/facil-pos/Langchain_Documentacion/blob/main/Pinecone/readme.md)

### Embeddings

[🧬 Embeddings | Chroma (trychroma.com)](https://docs.trychroma.com/embeddings)

[What are Vector Embeddings | Pinecone](https://www.pinecone.io/learn/vector-embeddings/)

Los algoritmos de inteligencia artificial necesitan de numeros para trabajar, a este conjunto de datos lo conocemos como dataset, muchas veces nos encontramos con dataset bien ordenados con columnas de valores numericos (Orden, categorizacion, ...etc), pero otras veces tenemos datos complejos de tratar como lo son textos, libros o documentacion compleja, es en este momento en el que necesitamos una manera de extraer la informacion de un texto y convertirla en una representacion numerica para que nuestra inteligencia artificial pueda trabajar sobre esta.

El concepto de Embedding, nos da una solucion a este problema, comprimiendo nuestra informacion o texto en una reprecentacion numerica con la que nuestros modelos de ML puedan trabajar sobre ella.

Un párrafo completo de texto o cualquier otro objeto se puede reducir a un vector. Incluso los datos numéricos se pueden convertir en vectores para facilitar las operaciones.

![Alt text](./Doc/DiagramaEmmbedding.png)

Pero hay algo especial en los vectores que los hace tan útiles. Esta representación permite traducir la similitud semántica percibida por los humanos a la proximidad en un espacio vectorial.

### Bases de datos vectoriales

Son bases de datos especializadas para el manejo y tratamiento de vectores.

Las bases de datos vectoriales tienen las capacidades de una base de datos tradicional y la especialización de tratar embeddings vectoriales, de la que carecen las bases de datos escalares tradicionales.

Con una base de datos vectorial, podemos añadir funciones avanzadas a nuestras IA, como recuperación de información semántica, memoria a largo plazo, etc. El diagrama siguiente nos permite comprender mejor el papel de las bases de datos vectoriales en este tipo de aplicaciones.

## Que es chroma DB?

Chroma DB es otra base de datos vectorial que cuenta cracteristicas propisas entre ellas son

- Open source
- Pensanda para trabajar con LLM
- Soporta diferentes opciones de almacenamiento subyacente como DuckDB para standalone o ClickHouse para escalabilidad.
- Proporciona SDK para Python y JavaScript/TypeScript.
- Se centra en la simplicidad, la velocidad y la posibilidad de análisis.
- Chroma DB ofrece una opción de servidor autoalojado.

![Funcionamiento de chromaDB](./doc/chromaDB.png)

## Instalacion de chroma DB

`Nota: Chroma requiere SQLite versión 3.35 o superior. Si experimenta problemas, actualice a Python 3.11 o instale una versión anterior de chromadb.`

[Aprendiendo a instalar SQLite en Windows | Sistek Peru](https://www.sistekperu.com/blog/aprendiendo-a-instalar-sqlite-en-windows)

### Instala paquete de python

```bash
pip install chromadb
```

### Como funciona chromaDB

1. En primer lugar, hay que crear una colección similar a las tablas de la base de datos de relaciones. Por defecto, Chroma convierte el texto en Embeddings utilizando all-MiniLM-L6-v2, pero puedes modificar la colección para utilizar otro modelo de incrustación [Como cambiar la funcion de emmbeddings](https://docs.trychroma.com/embeddings#default-all-minilm-l6-v2).

2. Añade documentos de texto a la colección recién creada con metadatos y un ID único. Cuando la colección recibe el texto, lo convierte automáticamente en incrustación.

3. Consulte la colección por texto o incrustación para recibir documentos similares. También puede filtrar los resultados en función de los metadatos.

# Primeros pasos con chromaDB

chromaDB nospermite tener muchos grados de personalizacion que aprenderemos poco a poco, en la siguiente activdad encontraremos los primeros pasos para el uso de chromaDB

[Introduccion.ipynb](introduccion.ipynb)

# Personalización

Como digimos anteriormente chroma permite varios grados de personalización, en los siguientes indices encontraras algunas de estas personalización.

## Embeddings coustom

Como sabemos chromaDB usa all-MiniLM-L6-v2 como motor de embeddings, pero esto se puede configurar

[Embeddings.ipynb](embeddings.ipynb)

## 