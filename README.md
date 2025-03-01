### **Prueba Técnica para Desarrollador Fullstack**

**Objetivo**: Evaluar habilidades en **Next.js 14**, **APIs REST**, **estado global**, **UI/UX**, **lógica de negocio** y **desarrollo en AWS con CDK**.

---

### **Parte 1: Gestión de Procedimientos Quirúrgicos (CRUD en Next.js 14)**

**Requisitos**:

1. Crear una API REST con **Next.js 14** para gestionar procedimientos quirúrgicos:

   - Endpoints: `GET /api/procedures`, `POST /api/procedures`, `PUT /api/procedures/:id`, `DELETE /api/procedures/:id`.
   - Validar datos con **Zod** (ej: `title` requerido, `prices` como array).

2. Frontend:
   - Tabla con **Shadcn UI** para listar procedimientos (ID, nombre, acciones).
   - Formulario con campos dinámicos para múltiples precios (usar **React Hook Form**).
   - Búsqueda y paginación con **React Query** y estado global (**Zustand**).

---

### **Parte 2: Generación de Cotizaciones**

**Requisitos**:

1. Formulario para:

   - Seleccionar cliente (nombre, email).
   - Agregar procedimientos desde la lista global (con selección de precio).
   - Calcular total con **IVA 19%** y descuento (campo numérico).

2. Exportar PDF con:
   - Logo de la empresa, tabla de procedimientos, totales y datos del cliente.
   - Usar **jsPDF** o **pdfmake**.

---

### **Parte 3: Implementación de API con AWS API Gateway + Lambda + CDK**

**Requisitos**:

1. Crear los endpoints en AWS API Gateway + Lambda usando **AWS CDK (TypeScript)**:

   - `GET /procedures` - Listar todos los procedimientos.
   - `POST /procedures` - Crear un procedimiento nuevo.
   - `PUT /procedures/{id}` - Actualizar un procedimiento existente.
   - `DELETE /procedures/{id}` - Eliminar un procedimiento.


> [!NOTE]
> usar aws sdk v3 https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/introduction/

2. Infraestructura con **AWS CDK**:
   - Crear una **tabla DynamoDB** para almacenar procedimientos quirúrgicos.
   - Implementar **Single Table Design** con partición basada en `PK = PROCEDURE#<id>`.
   - Dar permisos adecuados a la Lambda para interactuar con DynamoDB.
3. **Ejemplo de modelo de Single Table Design** (Solo como referencia, no es necesario implementarlo en la prueba):

```json
{
  "PK": "PROCEDURE#12345",
  "SK": "DETAILS",
  "title": "Cirugía de rodilla",
  "prices": [
    { "type": "Standard", "amount": 1500000 },
    { "type": "VIP", "amount": 2000000 }
  ],
  "createdAt": "2024-02-28T12:00:00Z"
}
```

4. **Plus:** Si el frontend puede conectarse a la API en AWS usando variables de entorno.

---

### **Parte 4: Evaluación de Código**

**Criterios**:

- **Legibilidad**: Estructura clara, componentes reutilizables.
- **Manejo de Estado**: Uso correcto de **Zustand** y **React Query**.
- **UI/UX**: Diseño responsive con **Tailwind CSS** y componentes de Shadcn.
- **Testing**: Al menos 1 test de integración (ej: CRUD de procedimientos).

---

### **Entrega**

1. Repositorio en GitHub con:
   - Código fuente (Next.js 14 + App Router + AWS CDK).
   - `README.md` con instrucciones de instalación y endpoints de la API.
2. **PDF de ejemplo** generado desde la aplicación.

---

**Nota:** Se evaluará la capacidad de estructurar el código, manejar datos de manera eficiente y seguir buenas prácticas en desarrollo Fullstack.

**Si tienes algún problema no dudes en contactarte por correo.**
