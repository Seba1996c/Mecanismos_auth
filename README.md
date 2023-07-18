# TheRialNews

## Descripción

"TheRialNews" es un sitio de noticias satíricas donde los usuarios pueden leer y comentar las publicaciones. Los usuarios registrados pueden dejar comentarios en las noticias. Además, cuenta con la capacidad de restablecer contraseñas a través de correo electrónico para los usuarios que olvidaron su contraseña.

## Configuración

Este proyecto utiliza Ruby on Rails, Devise para la autenticación de usuarios y PostgreSQL como base de datos.

Para poner en marcha el proyecto, sigue estos pasos:

1. Clona el repositorio:
    ```
    git clone https://github.com/<your-github-username>/TheRialNews.git
    ```

2. Navega al directorio del proyecto:
    ```
    cd TheRialNews
    ```

3. Instala las dependencias del proyecto:
    ```
    bundle install
    ```

4. Crea la base de datos y ejecuta las migraciones:
    ```
    rails db:create
    rails db:migrate
    ```

5. Inicia el servidor de Rails:
    ```
    rails server
    ```

## Restablecimiento de contraseñas

Para configurar el restablecimiento de contraseñas con Devise, debes configurar un servidor SMTP en `config/environments/development.rb` (para desarrollo) y/o `config/environments/production.rb` (para producción). La configuración debería ser similar a esto:

```ruby
config.action_mailer.delivery_method = :smtp
config.action_mailer.smtp_settings = {
  address: 'smtp.gmail.com',
  port: 587,
  domain: 'example.com',
  user_name: '<your-email>@example.com',
  password: '<your-password>',
  authentication: 'plain',
  enable_starttls_auto: true
}

