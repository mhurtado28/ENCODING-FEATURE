# ENCODING-FEATURE PARA MACHINE LEARNING :computer:
Aqui se presentan dos manera de realizar un Encoding a variables de tipo categoricas. Se presenta un bloque de codigo para el metodo de Label Encoding y otro para un One Hot Encoding


## LABEL ENCODING
```python
# Se descarga la siguiente librería para ejecutar el Label Encoding

from sklearn.preprocessing import LabelEncoder

# Agrupamos las variables numéricas y categóricas, cada una en dos nuevos Dataframes
 
num_data = df.select_dtypes(include=['int64', 'float64'])
cat_data = df.select_dtypes(include=['object'])

# Aplicando label encoding sobre las agrupaciones creadas

le = LabelEncoder()
cat_data = cat_data.apply(lambda col: le.fit_transform(col))

# Concatenamos el resultado del label encoding con las variables numéricas existentes

label_df = pd.concat([num_data, cat_data], axis = 1)
```
## ONE HOT ENCODING

```python
# Se agrupan las variables que son categóricas y se identifican el número de Targets (Etiquetas) que tiene la variable

encoding_col=[]
for i in df.select_dtypes(include='object'):   
    print(i,'-->',df[i].nunique())
    encoding_col.append(i)

# Hacemos una copia del dataset cargado para aplicar el metodo One Hot Encoding

df_onehot = df.copy()

# Aplicamos el metodo One Hot Encoding con la librería de Pandas y el comando "pd.get_dummmies"

df_onehot = pd.get_dummies(df_onehot, drop_first=True, columns = encoding_col, prefix = encoding_col)
```

------------

##  **English** 🇬🇧 

------------

# ENCODING-FEATURE FOR MACHINE LEARNING :computer:
Here are two ways to perform an Encoding to variables of categorical type. A code block is presented for the Label Encoding method and in the other way for a One Hot Encoding


## LABEL ENCODING
```python
# Next library is downloaded to execute the Label Encoding

from sklearn.preprocessing import LabelEncoder

# We group the numeric and categorical variables, each one in two different Dataframes
 
num_data = df.select_dtypes(include=['int64', 'float64'])
cat_data = df.select_dtypes(include=['object'])

# Applying label encoding on the created groupings

le = LabelEncoder()
cat_data = cat_data.apply(lambda col: le.fit_transform(col))

# Concatenate the result of the encoding label with the existing numeric variables

label_df = pd.concat([num_data, cat_data], axis = 1)
```


## ONE HOT ENCODING

```python
# Se agrupan las variables que son categóricas y se identifican el número de Targets (Etiquetas) que tiene la variable

encoding_col=[]
for i in df.select_dtypes(include='object'):   
    print(i,'-->',df[i].nunique())
    encoding_col.append(i)

# Hacemos una copia del dataset cargado para aplicar el metodo One Hot Encoding

df_onehot = df.copy()

# Aplicamos el metodo One Hot Encoding con la librería de Pandas y el comando "pd.get_dummmies"

df_onehot = pd.get_dummies(df_onehot, drop_first=True, columns = encoding_col, prefix = encoding_col)
```


