# ENCODING-FEATURE PARA MACHINE LEARNING :computer:
Aqui se presentan dos manera de realizar un Encoding a variables de tipo categoricas. Se presenta un bloque de codigo para el metodo de Label Encoding y otro para un One Hot Encoding


**Table of Contents**

[TOCM]

[TOC]

#H1 header
##H2 lABEL ENCODING
##H3 ONE HOT ENCODING

#Heading 1 link [Heading link](https://github.com/pandao/editor.md "Heading link")
##Heading 2 link [Heading link](https://github.com/pandao/editor.md "Heading link")
##Heading 3 link [Heading link](https://github.com/pandao/editor.md "Heading link")


## LABEL ENCODING
```python
#APLICAMOS EL METODO DE LABEL ENCODING A NUESTRO SET DE DATOS 
from sklearn.preprocessing import LabelEncoder

 #Agrupamos las variables numéricas y categóricas, cada una en dos nuevos Dataframes
 
num_data = df.select_dtypes(include=['int64', 'float64'])
cat_data = df.select_dtypes(include=['object'])

# Aplicando label encoding sobre las agrupaciones creadas

le = LabelEncoder()
cat_data = cat_data.apply(lambda col: le.fit_transform(col))

#Concatenamos el resultado del label encoding con las variables numéricas existentes

label_df = pd.concat([num_data, cat_data], axis = 1)
```
## ONE HOT ENCODING

**Table of Contents**

[TOCM]

[TOC]

#H1 header
##H2 lABEL ENCODING
##H3 ONE HOT ENCODING



# ENCODING-FEATURE FOR MACHINE LEARNING :computer:
Here are two ways to perform an Encoding to variables of categorical type. A code block is presented for the Label Encoding method and in the other way for a One Hot Encoding
