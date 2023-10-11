# Exportaciones e importaciones mundiales (1988-2021)

Holaa!!! diviértete navegando por mi proyecto final <3


# Presentación 

La presentación para mostrar la información utilizada del set de datos, las conclusiones sacadas del análisis realizado y algunas visualizaciones (realizadas en Power BI) 
**offline!**
[Exportaciones e importaciones mundiales - Presentaciones de Google](https://docs.google.com/presentation/d/1tnXneHcZEqYCISk7WebSuYg-bH75Vvq6sC_BSgrJC5c/edit#slide=id.ge9090756a_1_267)

## Descripción del proyecto

El siguiente Dataset es una recopilación datos relacionados con el comercio internacional y las políticas comerciales. Este conjunto de datos está diseñado para proporcionar información y análisis a investigadores, responsables de la formulación de políticas y analistas interesados en comprender la dinámica del comercio mundial. Abarca diversos aspectos del comercio, incluidos los valores comerciales, los tipos arancelarios y los indicadores de política comercial de numerosos países a lo largo de varios años.

## Queries y Scripts de Phyton usados

Colab: "https://colab.research.google.com/drive/1mOzX6twBSj8pGyQ91ApaqLmaBtNuF2i9?usp=sharing"

#Instalar librería para abrir datasets
!pip install opendatasets
import opendatasets as od



#Asignar link del dataset a dataset_link
dataset_link= "https://www.kaggle.com/datasets/muhammadtalhaawan/world-export-and-import-dataset"
od.download(dataset_link)



#Copiar ruta de acceso de los archivos
import os
os.chdir("world-export-and-import-dataset")
os.listdir()



#Asignamos nombre al Dataframe y separamos los datos por ","
import pandas as pd
csv_path="34_years_world_export_import_dataset.csv"
df = pd.read_csv(csv_path,sep=",")



#Mostramos los datos del dataset
headers = ["Partner Name","Year","Export (US$ Thousand)","Import (US$ Thousand)","Export Product Share (%)","Import Product Share (%)","Revealed comparative advantage","World Growth (%)","Country Growth (%)","AHS Simple Average (%)","AHS Weighted Average (%)","AHS Total Tariff Lines","AHS Dutiable Tariff Lines Share (%)","AHS Duty Free Tariff Lines Share (%)","AHS Specific Tariff Lines Share (%)","AHS AVE Tariff Lines Share (%)","AHS MaxRate (%)","AHS MinRate (%)","AHS SpecificDuty Imports (US$ Thousand)","AHS Dutiable Imports (US$ Thousand)","AHS Duty Free Imports (US$ Thousand)","MFN Simple Average (%)","MFN Weighted Average (%)","MFN Total Tariff Lines","MFN Dutiable Tariff Lines Share (%)","MFN Duty Free Tariff Lines Share (%)","MFN Specific Tariff Lines Share (%)","MFN AVE Tariff Lines Share (%)","MFN MaxRate (%)","MFN MinRate (%)","MFN SpecificDuty Imports (US$ Thousand)","MFN Dutiable Imports (US$ Thousand)","MFN Duty Free Imports (US$ Thousand)"]
df.columns = headers
df.head()



#Calcula en general el conjunto de datos total
df.shape



#Revisamos los tipos de datos de cada valor
df.dtypes



#Verificar si existen datos duplicados
check_dup = df.duplicated().any()
print("¿Existen valores duplicados en los datos?",check_dup)
if check_dup:
  df = df.drop_duplicates()
  print("Los valores duplicados fueron eliminados")
else :
  print("No hay valores duplicados en los datos")



#Muestra las celdas vacías o en N/A de cada columna
print(df.isnull().sum())
## Enlace del Dataset elegido

[World Export & Import Dataset (1989 - 2023) (kaggle.com)](https://www.kaggle.com/datasets/muhammadtalhaawan/world-export-and-import-dataset)


# Documentación

Toda la información sacada del Dataset tal como conclusiones, términos aprendidos, tecnologías usadas y toda esa información importante que no fue colocada en los anteriores link o archivos para no saturar, se encuentran en este informe / documento.

https://docs.google.com/document/d/1VQ9mEYxUSomWmmUFyxNU182Hb59-9L5y/edit?usp=sharing&ouid=104817640595721035130&rtpof=true&sd=true
