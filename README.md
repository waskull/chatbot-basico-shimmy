# Instrucciones para usar [Shimmy](https://github.com/Michael-A-Kuykendall/shimmy)

## Descargar modelo en formato .gguf.
Puede ser: [Gemma 3 1B](https://huggingface.co/ggml-org/gemma-3-1b-it-GGUF/resolve/main/gemma-3-1b-it-Q8_0.gguf?download=true)

Colocar el modelo en la carpeta models

# Situarse en la carpeta donde descomprimieron el repositorio y escribir en el cmd:
<code>shimmy.exe serve --bind 0.0.0.0:11434</code>

![Shimmy (Levantando Servidor Shimmy)](/imagenes/shimmy.png)

Luego ir a la carpeta 'chatbot-django', iniciar el entorno virtual 'venv', instalar las dependencias con <code>pip install -r requirements.txt</code>, iniciar el proyecto con <code>python manage.py runserver 0.0.0.0:8000</code>
Logearse en Django con el endpoint [http://localhost:8000/api/login/](http://localhost:8000/api/login/) -> Peticion POST
Y enviar este JSON:
```json
{
  "username":"admin",
  "password":"1234",
}
```
Luego hacer una peticion POST al endpoint [http://localhost:8000/api/chatbot/](http://localhost:8000/api/chatbot/)

con el siguiente JSON:
```json
{
  "pregunta":"dame informacion de los envios",
  "modelo":"gemma-3-1b-it-Q8_0"
}
```

![Yaak (Peticion POST con Yaak)](/imagenes/yaak.png)
