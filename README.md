
# byCarket - Documentación del Proyecto

### Flujo de trabajo
1. Crear una nueva rama para cada característica o corrección
2. Desarrollar y probar localmente
3. Asegurarse de que el código sigue las convenciones establecidas
4. Crear un Pull Request para revisión
5. Después de la aprobación, fusionar con la rama development
6. Semanalmente se mergeara todo lo que contenga development con la rama main para producción

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
npm run dev
```


### Idioma
- **Código**: Todo el código (variables, funciones, nombres de archivos, etc.) debe estar en inglés.
- **Interfaz de Usuario**: Todos los textos visibles para el usuario final deben estar en español.

### Nomenclatura
- **Componentes**: PascalCase (ej. `UserProfile.tsx`)
- **Funciones**: camelCase (ej. `getUserData()`)
- **Variables**: camelCase (ej. `userData`)
- **Constantes**: UPPER_SNAKE_CASE (ej. `API_URL`)


### Arquitectura de Desarrollo
Componentes de servidor: Todas las páginas se desarrollarán como componentes de servidor por default

Estructura de importación: Cada página importará una vista (view) principal, y esta vista importará todos los componentes necesarios

### Modularización
Componentes reutilizables: Priorizamos la creación de componentes modulares y reutilizables

### Carpetas
- `components`: Contiene todos los componentes reutilizables, y subcarpetas por categoría
- `contexts`: Contiene los contextos del sitio web
- `pages`: Contiene las páginas principales del sitio
- `views`: Contiene las vistas principales de cada página
- `utils`: Contiene funciones y utilidades reutilizables
-`services`: Contiene servicios de conexión a la base de datos y configuraciones del navegador

### Directiva "use client"
Utilizaremos la directiva "use client" exclusivamente cuando sea necesario para:
- Componentes que requieran interactividad del lado del cliente
- Componentes que utilicen hooks de React
- Componentes que manejen eventos del usuario

## Estándares de Comentarios

### Better Comments (EXTENSION INSTALAR)
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

## Sistema de gestión de pagos
URL: https://docs.vexorpay.com/en/docs/core/get-started

### FORMULARIOS DEL FRONT
- **Biblioteca**: Todos los formularios se implementan con Formik
- **Validaciones**: Todas las validaciones se realizan con Yup
- **Validaciones personalizadas**: Se pueden implementar expresiones regulares (regex) según las necesidades específicas de cada campo
- **Estructura recomendada**:
  ```jsx
  const validationSchema = Yup.object({
    fieldName: Yup.string().required('Campo requerido')
  });
  
  const FormComponent = () => {
    return (
      <Formik
        initialValues={initialValues}
        validationSchema={validationSchema}
        onSubmit={handleSubmit}
      >
        {/* Contenido del formulario */}
      </Formik>
    );
  };