FROM drupal

# Al poner una \ se se puede continuar en la linea siguiente
# rm -rf /var/lib/apt/lists/* sirve para borrar el cache de apt, se salvan como 10MB

RUN apt-get update && apt-get install -y git \
&& rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html/themes

# Al hacer un git clone baja todo el repositorio (todo su historial y modificaciones)y puede tardar un monton
# Poniendo --branch 8.x-3.x --single-branch --depth 1 conseguimos que baje solo el branch que necesitamos y nada mas. Ahorramos mucho tiempo

# El chown es para asignar los permisos a la nueva carpeta ya que automaticamnte cuando hago el git clone me lo crea 
# como root. Pero el apache necesita que los permisos sean para www-data

RUN git clone --branch 8.x-3.x --single-branch --depth 1 https://git.drupal.org/project/bootstrap.git \
&& chown -R www-data:www-data bootstrap

WORKDIR /var/www/html