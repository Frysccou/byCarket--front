
# byCarket - Documentación del Proyecto

### Idioma
- **Código**: Todo el código (variables, funciones, nombres de archivos, etc.) debe estar en inglés.
- **Interfaz de Usuario**: Todos los textos visibles para el usuario final deben estar en español.

### Nomenclatura
- **Componentes**: PascalCase (ej. `UserProfile.jsx`)
- **Funciones**: camelCase (ej. `getUserData()`)
- **Variables**: camelCase (ej. `userData`)
- **Constantes**: UPPER_SNAKE_CASE (ej. `API_URL`)

## Estándares de Comentarios

### Better Comments
Utilizamos la extensión Better Comments para mejorar la legibilidad de nuestros comentarios. Los prefijos son:

- `!` - Para comentarios críticos o advertencias importantes
```javascript
// ! Cuidado: Esta función modifica el estado global
```

- `?` - Para preguntas o aspectos que requieren revisión
```javascript
// ? ¿Deberíamos manejar este caso de borde?
```

- `*` - Para resaltar información importante o notas
```javascript
// * Esta función requiere autenticación previa
```

### Comentarios de Equipo
Para facilitar la comunicación dentro del equipo, utilizamos el siguiente formato:

- `[Fran a x]` - Comentarios dirigidos a un miembro específico del equipo

- `[Fran a equipo]` - Comentarios dirigidos a todo el equipo

## Autenticación con Auth0

Utilizamos Auth0 para gestionar la autenticación de usuarios. A continuación se presentan los recursos oficiales:

- [Documentación oficial de Auth0](https://auth0.com/docs)
- [Manejo de roles y permisos](https://auth0.com/docs/authorization/rbac)

### Instalación
1. Clonar el repositorio:
```bash
git clone [URL_DEL_REPOSITORIO]
cd byCarket--front
```

2. Instalar dependencias:
```bash
npm install
```

3. Configurar variables de entorno:
   - Crear archivo `.env` basado en `.env.example`
   - Configurar las credenciales de Auth0 y otras variables necesarias

4. Iniciar el servidor de desarrollo:
```bash
npm start
```

### Flujo de trabajo
1. Crear una nueva rama para cada característica o corrección
2. Desarrollar y probar localmente
3. Asegurarse de que el código sigue las convenciones establecidas
4. Crear un Pull Request para revisión
5. Después de la aprobación, fusionar con la rama principal
