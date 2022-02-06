Los endpoints de la API que deberás entregar al finalizar este módulo son los siguientes:

- **POST /auth**
  Recibe un email y encuentra/crea un user con ese email y le envía un código vía email.
- **POST /auth/token**
  Recibe un email y un código y valida que sean los correctos. En el caso de que sean correctos devuelve un token e invalida el código.
- **GET /me**
  Devuelve info del user asociado a ese token
- **PATCH /me**
  Permite modificar algunos datos del usuario al que pertenezca el token usado en el request.
- **PATCH /me/address**
  Permite modificar un dato puntual del usuario al que pertenezca el token usado en el request. En este caso el objeto que describe la dirección.
- **GET /search?q=query&offset=0&limit=10**
  Buscar productos en nuestra base de datos. Chequea stock y todo lo necesario.
- **GET /products/{id}**
  Obtiene toda data de un producto.
- **POST /order?productId={id}**
  Genera una compra en nuestra base de datos y además genera una orden de pago en MercadoPago. Devuelve una URL de MercadoPago a donde vamos a redigirigir al user para que pague.
- **POST /ipn/mercadopago**
  Recibe la señal de MercadoPago para confirmar que el pago fué realizado con éxito. Cambia el estado de la compra en nuestra base y le envía un email al usuario para avisarle que el pago se realizó correctamente. También se debe generar algún aviso hacia quienes deban procesar esta compra. Esto es algo interno así que puede ser un email o un registro en Airtable.
