<h1>Sistema de Gestión de Biblioteca</h1>

1. *Gestión de libros:*
    - **Añadir libros:**
    Introducir los detalles de un nuevo libro en la base de datos. Esto podría incluir el título del libro, el autor, el género, la cantidad de copias disponibles, etc. 
    `addBook(title, author, genre, copies)`.
    - **Eliminar libros:** 
    Eliminar un libro de la base de datos si ya no está disponible en la biblioteca. 
    `deleteBook(bookId)` toma el ID del libro como parámetro y lo elimina de la base de datos.
    - **Actualizar libros:** 
    Actualizar los detalles de un libro, como aumentar o disminuir la cantidad de copias disponibles. 
    `updateBook(bookId, newDetails)` que toma el ID del libro y los nuevos detalles como parámetros y actualiza el libro en la base de datos.
    - **Buscar libros:** Los usuarios pueden buscar libros por título, autor, género, etc. 
    `searchBooks(query)` que tome una consulta de búsqueda como parámetro y devuelva una lista de libros que coincidan con la consulta.

2. **Gestión de usuarios:**
    - **Añadir usuarios:** Añadir nuevos usuarios a la base de datos. Esto podría incluir su nombre, dirección de correo electrónico, contraseña, etc.
    `addUser(name, email, password)`.
    - **Eliminar usuarios:** 
    Eliminar usuarios de la base de datos. 
    `deleteUser(userId)` que toma el ID del usuario como parámetro y lo elimina de la base de datos.
    - **Actualizar usuarios:** 
    Actualizar los detalles de un usuario, como cambiar su dirección de correo electrónico o contraseña. 
    `updateUser(userId, newDetails)` que toma el ID del usuario y los nuevos detalles como parámetros y actualiza el usuario en la base de datos.
    - **Buscar usuarios:** Buscar usuarios por su nombre o dirección de correo electrónico. 
    `searchUsers(query)` que toma una consulta de búsqueda como parámetro y devuelve una lista de usuarios que coincidan con la consulta.

3. **Reserva de libros:** 
    - Los usuarios pueden reservar un libro si está disponible. Cuando un libro es reservado, la cantidad de copias disponibles de ese libro disminuye en uno. 
    `reserveBook(userId, bookId)` que toma el ID del usuario y el ID del libro como parámetros, marca el libro como reservado por el usuario y disminuye la cantidad de copias disponibles del libro en uno.
    - Si un libro no está disponible, el usuario será notificado, también lo será cuando el libro esté disponible de nuevo. 
    `notifyWhenAvailable(userId, bookId)` que toma el ID del usuario y el ID del libro como parámetros y añade al usuario a una lista de espera para ese libro.

4. **Devolución de libros:** 
    - Cuando un usuario devuelve un libro, la cantidad de copias disponibles de ese libro aumenta en uno. 
    `returnBook(userId, bookId)` que toma el ID del usuario y el ID del libro como parámetros, marca el libro como no reservado por el usuario y aumenta la cantidad de copias disponibles del libro en uno.

5. **Autenticación y autorización:** 
    - Sistema de inicio de sesión para los usuarios y administradores.
    `login(email, password)` que toma la dirección de correo electrónico y la contraseña como parámetros y devuelve un token de autenticación si las credenciales son correctas.
    - Los administradores tienen permisos para gestionar libros y usuarios, mientras que los usuarios sólo pueden reservar y devolver libros.
    `authorize(userId, action)` que tome el ID del usuario y la acción que quiere realizar como parámetros y devuelva `true` si el usuario tiene permiso para realizar la acción y `false` en caso contrario.