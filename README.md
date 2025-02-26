# 📈 Proyecto_ETL

## 📖 Descripción

El objetivo del proyecto es procesar y analizar los datos de reservas hoteleras en Madrid. El archivo de entrada contiene información sobre reservas de hoteles propios y de la competencia. Nuestro enfoque se centra en la extracción, transformación y carga (ETL) de estos datos para generar información valiosa sobre la ocupación de nuestros hoteles, de la competencia y la relación con eventos en la ciudad de Madrid.

Para esto, se extraerá información sobre hoteles competidores mediante web scraping y se enriquecerán los datos de las reservas con eventos locales proporcionados por la API del Ayuntamiento de Madrid.

## 🗂️ Estructura del Proyecto

El proyecto se estructura teniendo en cuenta las diferentes fases del proceso de ETL:

**1. Extracción de datos:**
   - Análisis del archivo reservas_hoteles.parquet.
Se extraerán los datos de reservas de hoteles, tanto los propios como los que existan de la competencia.

  - Realización de web scrapping de la url de  los hoteles Ibis.
Extracción de la información de los 10 primeros hoteles, que nos ampliará y completará la información de la competencia.

  - Consulta de  la API del Ayuntamiento de Madrid.
Lo que se esperaba de este paso era la obtención de eventos en la ciudad de Madrid durante las fechas de las reservas en el archivo proporcionado, para enriquecer nuestra base de datos.

**2. Transformación de los datos:**
  - Limpieza de los datos extraídos de las tres fuentes mencionadas anteriormente para asegurar que sean comparables.
Para ello, hemos revisado cuáles eran las columnas que era necesario asignar un ID único (hoteles y clientes).
Posteriormente, hemos revisado si  habían valores nulos, y se ha decidido rellenarlos usando la media de cada hotel, revisando los outliers (estrellas y precio noche).
Finalmente, se han revisado los valores nulos pero de los que disponíamos de la información y se han rellenado (ciudad y fecha de reserva).

  - Enriquecimiento de los datos, asociando los datos de las reservas hoteleras con los eventos disponibles durante esas fechas, permitiendo la correlación entre la ocupación de los hoteles con los eventos en Madrid.

**3. Carga de datos:**
   - Una vez transformados los datos de las diferentes fuentes, se ha procedido al almacenamiento en una base de datos SQL para facilitar consultas, análisis e integridad de los datos.

## 📊 Resultados y Conclusiones

Mediante el proceso de ETL conseguimos tener un análisis competitivo, comparando las reservas de nuestros hoteles con los de la competencia y por ello enriqueciendo nuestros datos. Podremos identificar tendecias de precios, ocupación y valoración de los clientes. Esta información es valiosa para poder mejorar nuestra estrategía de marketing y de precios.

Además, al haber enriquecido los datos con la información de eventos en Madrid, podremos analizar si hay una correlación y como afectan estos eventos a la ocupación hotelera. Con esto, podremos tomar decisiones estratégicas para mejorar la ocupación durante eventos clave en Madrid.

Por último, con la información obtenida también podremos tener una mejor previsión de la demanda y hacer una asignación de personal más eficiente dentro de nuestros hoteles.


## 🔄 Próximos Pasos

Al dar error los ID de hotel en la tabla de reservas y hoteles, se ha modificado en ambos Dataframes.  
Habria que revisar la integridad de los id en ambos y que ocncuerden.

Con los datos obtenidos se podría analizar el impacto que tienen los eventos cercanos a los hoteles en sus reservas.
Tambien se podrían obtener datos de relevancia para los hoteles por el perfil del cliente.



## 🤝 Contribuciones
Las contribuciones son bienvenidas. Si deseas mejorar el proyecto, por favor abre un pull request o una issue.

## ✒️ Autores
Antonio Martínez Urbán - @AntonioHackio