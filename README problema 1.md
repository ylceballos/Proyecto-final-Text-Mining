# Examen Final — Proyecto de Análisis de Tweets

## Descripción
El objetivo principal es analizar un dataset de tweets, identificar los **usuarios más citados** y comprender las **razones por las que son mencionados**, a través de procesamiento de lenguaje natural (NLP).

## Contenido
- `Proyecto_Final_YC.ipynb`: Notebook principal con todo el flujo de trabajo y resultados.
- `outputs_p1/`: Carpeta generada automáticamente que contiene:
  - `corpus_<usuario>.csv` → Corpus de tweets de cada usuario más citado.
  - `top10_context_<usuario>.csv` → Tokens del contexto más frecuentes alrededor de cada mención.
- `README.md`: Este archivo con la documentación del proyecto.

## Flujo de trabajo
1. **Carga de datos**: Lectura de los tweets desde el archivo original.
2. **Preprocesamiento**:
   - Remoción de stopwords.
   - Normalización de texto (lowercase, lematización, stemming).
   - Manejo de codificación (UTF-8, Latin1, etc).
3. **Identificación de usuarios más citados**: Detección de las menciones con mayor frecuencia.
4. **Construcción de corpus**: Generación de un corpus para cada usuario top-3.
5. **Extracción de contexto**: Tokens ±5 alrededor de la mención.
6. **Visualización**: WordCloud para cada usuario.
7. **Análisis de razones de citación**: Justificación de por qué los usuarios fueron mencionados, en función de los tokens más frecuentes.

## Resultados principales
- **@mileycyrus** → Citada principalmente por **expresiones de apoyo y movilización de votos** (tokens: *love, vote, hope, luck, amazing*).  
- **@tommcfly** → Citado por **interacción cercana con fans** (tokens: *say, hey, please, reply, birthday, love*).  
- **@ddlovato** → Citada por **fandom, ánimo y llamados a acción** (tokens: *love, wish, please, come, vote, awesome*).  

## Requisitos
Para ejecutar el notebook asegúrese de instalar las siguientes librerías en su entorno:

```bash
pip install pandas numpy nltk spacy wordcloud langdetect unidecode matplotlib
python -m spacy download es_core_news_sm
python -m spacy download en_core_web_sm
