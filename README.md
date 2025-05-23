# python_nmap
Script pequeño que integra nmap con Python para hacer búsqueda de hosts, puertos y servicios. Permite el uso de la API de ChatGPT para analizar cuáles hosts son más vulnerables, y las próximas etapas en un ejercicio de hacking ético.
Como el uso de la API de ChatGPT es paga, se cobra por los tokens utilizados (importante) en la consulta. 

# Instalación

El proyecto se puede obtener mediante git a través del comando:
```
git clone https://github.com/Andrein99/python_nmap.git
```
Luego de descargar los archivos del repositorio, es recomendado crear un entorno virtual para que no hayan problemas de compatibilidad al realizar la instalación de las dependencias. Luego de abrir la terminal en la carpeta del proyecto, la forma recomendada de instalación sería para Linux:
```
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
Para Windows cambiaría la activación del entorno virtual:
```
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```
Con las dependencias ya instaladas, se debe abrir el archivo .env y asignar la API key del usuario a la variable OPEN_API_KEY (la variable por defecto de la API).

# Uso
El script se utiliza al llamar las funciones que se encuentran en el condición al final del código. Se debe modificar según el uso que se le quiera dar al script (por defecto utiliza la API de ChatGPT entonces va producir un error si no se asigna en el archivo .env).
También es importante cambiar la IP que se puso como placeholder por la red (junto a su submáscara de red en notación CIDR IPv4) de interés para que sea analizada.
Si se quiere usar un modelo diferente al que está por default "gpt-4-0125-preview" para aminorar los costos, o para tener un resultado específico, se puede modificar la función priorizar_hosts.

# Problemas comunes
En Linux es necesario utilizar ``` sudo ``` para ejecutar el script debido a la funcionalidad propia de nmap (en especial si el descubrimiento o análisis que se quiere realizar contiene hosts Windows en la red). Esto puede producir un error en el que algunas de las dependencias parecen no haber sido instaladas. Esto ocurre debido al uso de privilegios elevados, donde se puede hacer uso de un intérprete de Python que es diferente al del entorno virtual creado. Para solucionarlo basta con ejecutar el script usando el Python que se encuentra en el entorno virtual en la ruta (según la recomendación en la sección de instalación) ``` .venv/bin/python ``` para Linux.

# Disclaimer
Este programa es publicado con el objetivo de servir un propósito educativo y mejorar la securidad de los sistemas. No soy responsable por el mal uso del proyecto.

# Contacto
[corrgom@gmail.com]
