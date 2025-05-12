
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

  # Configuración de Colores y Fuentes Globales

Este documento describe la configuración de colores y fuentes que debemos priorizar y utilizar consistentemente en nuestro proyecto.

## Colores Base (Definidos en `:root`)

Hemos definido los siguientes colores base en la sección `:root` de nuestro archivo CSS global:

```css
:root {
    --principal-blue: #103663;
    --secondary-blue: #4A77A8;
}
--principal-blue: #103663 - Este es nuestro color azul principal de la marca. Debe ser utilizado como color base para elementos importantes, como fondos principales, acentos primarios y cualquier lugar donde queramos destacar la identidad de la marca.

--secondary-blue: #4A77A8 - Esta es una tonalidad más clara de nuestro azul principal, pensada para detalles, acentos secundarios o elementos que necesiten diferenciarse ligeramente del color principal sin perder la coherencia visual.

Prioridad de Uso: Siempre que necesitemos aplicar los colores base de la marca, debemos utilizar estas variables CSS (var(--principal-blue) y var(--secondary-blue)) para asegurar la consistencia en toda la aplicación.

Fuentes (Importadas)
Hemos importado las siguientes fuentes de Google Fonts para diferentes propósitos:

CSS

/* Fuente 1: Be Vietnam Pro - Para botones y elementos de la interfaz */
@import url('[https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap](https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap)');

/* Fuente 2: Climate Crisis - Para títulos principales */
@import url('[https://fonts.googleapis.com/css2?family=Climate+Crisis&display=swap](https://fonts.googleapis.com/css2?family=Climate+Crisis&display=swap)');

/* Fuente 3: Questrial - Para subtítulos */
@import url('[https://fonts.googleapis.com/css2?family=Questrial&display=swap](https://fonts.googleapis.com/css2?family=Questrial&display=swap)');

/* Fuente 4: Inter - Para números o porcentajes */
@import url('[https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap](https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap)');
Be Vietnam Pro: Utilizar principalmente para el texto de los botones y otros elementos de la interfaz de usuario donde la legibilidad y un estilo moderno son importantes.

Climate Crisis: Reservada para los títulos principales. Su estilo distintivo ayudará a que los encabezados de sección o página resalten.

Questrial: Ideal para subtítulos, proporcionando una lectura clara y complementando los títulos.

Inter: Destinada para la visualización de números o porcentajes, ofreciendo una tipografía con buena claridad para datos.

Prioridad de Uso: Al aplicar estilos de texto, debemos priorizar el uso de estas fuentes según el propósito indicado. Esto ayudará a mantener una jerarquía visual clara y una estética consistente en toda la aplicación.

Recuerda que esta configuración de colores y fuentes es fundamental para la identidad visual de nuestra aplicación. Siempre que sea posible, utilicemos estas definiciones para mantener la coherencia.