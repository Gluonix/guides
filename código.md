Ruby
====

- Todo el código es en idioma inglés.
- Usa doble punto en lugar de _hash rockets_.
  Ejemplo correcto:
  `{ key: value }`

  Ejemplo incorrecto
  `{ key => value }`


Variables y Métodos
-------------------

- Usa nombres descriptivos, evita abreviaciones.
- Usa snake_case para nombrar la variable (guiones bajos para separar palabras).

  Ejemplo incorrecto:
  ```ruby
  a1 = 5
  abc = 5
  ```

  Ejemplo correcto:
  ```ruby
  pi_number = 3.1415

  def some_method
    ...
  end
  ```

Clases y Módulos
----------------

- Usa nombres descriptivos, evita abreviaciones.
- No incluyas el tipo en el nombre (SearchClass, VotableModule).
- Usa CamelCase (mayúsculas para separar palabras).
- Si vas a usar acrónimos como HTTP, JSON y XML, escríbelo en mayúsculas.

```ruby
class UserSession
  ...
end
```

Comentarios
-----------
Escribe comentarios descriptivos del comportamiento a lo largo del código.


Sangría y Espacios en Blanco
----------------------------
- Usa dos espacios en lugar de tabulaciones.
- Inserta dos espacios (no sangrías) cada vez que se abra una llave.
- Separa cada sección con al menos un espacio.

Colecciones
-----------

- Para la creación de arreglos y hashes, usa los corchetes o llaves.

  Ejemplo incorrecto:
  ```ruby
  arr = Array.new
  hash = Hash.new
  ```

  Ejemplo correcto:
  ```ruby
  arr = []
  hash = {}
  ```

- Usa símbolos en lugar de cadena de caracteres como llaves hash.
  Ejemplo incorrecto:
  ```ruby
  hash = { 'one' => 1, 'two' => 2, 'three' => 3 }
  ```
  Ejemplo correcto:
  ```ruby
  hash = { one: 1, two: 2, three: 3 }
  ```

- Usa each para procesar los elementos de un arreglo.
  Ejemplo incorrecto:
  ```ruby
  for elem in arr do
    puts elem
  end
  ```
  Ejemplo correcto:
  ```ruby
  arr.each { |elem| puts elem }
  ```


Rails
=====

Vistas
-----

- Evita usar variables locales en vistas.
- No hagas llamadas a la base de datos desde la vista.
- Usa vista parciales cuando sea apropiado.
- No incluyas mucha lógica en la vista, de ser necesario escribe un método en los helpers.

Modelos
------
- Evita ignorar validaciones al guardar
- Escribe métodos en los modelos para hacer queries complejos
- Utiliza scopes para especificar queries usados comúnmente, por ejemplo
```ruby
scope :active, -> { where(is_active: true) }
```

Migraciones
----------
- El nombre de la migración debe empezar con un verbo.
- Fija un valor por default para los campos booleanos.
- Si se necesita un valor por default debe estar declarado desde la migración y no en el modelo.

Rutas & Misc.
------
- Evita anidar rutas más de un nivel, para esto utiliza _shallow nesting_ cuando sea necesario.
- Usa el sufijo `_url` en vistas de correos, en otros casos usa el sufijo `_path`.


Guía para usar git
==================

- El mensaje del _commit_ debe ser descriptivo.
- Empieza el mensaje del commit con un verbo, como agregar, quitar, actualizar, etc.
- Elimina el _branch_ de manera local y remota una vez que se hizo _merge_.
- Toda nueva característica debe ser construida en una nueva _branch_.
- Elimina del working tree cualquier archivo específico a tu máquina local de desarrollo, como .DS_Store, .log, etc.
- Cada integración de código debe ser a través de un _pull request_.


Pull Request
------------
Aunque el equipo de desarrollo esté compuesto por un solo miembro, debe abrir un *pull request* para integrar código a la aplicación desarrollada.
- Utiliza títulos descriptivos para identificar el _pull request_.
- Escribe una descripción con las tareas completadas o características nuevas.
- En el caso de que el pull request esté ligado a una tarjeta en Trello, u otra plataforma, incluye la liga en la descripción.
Ejemplo:
```
Changed the navigation bar color to red
[Card](www.liga-a-tarjeta.com/num-tarjeta)
```
- Si el pull request no está listo para ser revisado, escribe `[WIP]` (Work in Progress) en el título, y edítalo cuando termines de trabajar en él.
Ejemplo:
`[WIP] Add translations`
