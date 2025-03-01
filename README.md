### **Prueba Técnica para Desarrollador Fullstack**  
**Objetivo**: Evaluar habilidades en **Next.js 14**, **APIs REST**, **estado global**, **UI/UX**, y **lógica de negocio**.

---

#### **Parte 1: Gestión de Procedimientos Quirúrgicos (CRUD)**  
**Requisitos**:  
1. Crear una API REST con **Next.js 14** para gestionar procedimientos quirúrgicos:  
   - Endpoints: `GET /api/procedures`, `POST /api/procedures`, `PUT /api/procedures/:id`, `DELETE /api/procedures/:id` 
   - Validar datos con **Zod** (ej: `title` requerido, `prices` como array) 

2. Frontend:  
   - Tabla con **Shadcn UI** para listar procedimientos (ID, nombre, acciones)
   - Formulario con campos dinámicos para múltiples precios (usar **React Hook Form**)
   - Búsqueda y paginación con **React Query** y estado global (**Zustand**)

---

#### **Parte 2: Generación de Cotizaciones**  
**Requisitos**:  
1. Formulario para:  
   - Seleccionar cliente (nombre, email).  
   - Agregar procedimientos desde la lista global (con selección de precio) 
   - Calcular total con **IVA 19%** y descuento (campo numérico).  

2. Exportar PDF con:  
   - Logo de la empresa, tabla de procedimientos, totales y datos del cliente.  
   - Usar **jsPDF** o **pdfmake** 

---

#### **Parte 3: Evaluación de Código**  
**Criterios**:  
- **Legibilidad**: Estructura clara, componentes reutilizables 
- **Manejo de Estado**: Uso correcto de **Zustand** y **React Query**
- **UI/UX**: Diseño responsive con **Tailwind CSS** y componentes de Shadcn
- **Testing**: Al menos 1 test de integración (ej: CRUD de procedimientos)

---

#### **Entrega**  
1. Repositorio en GitHub con:  
   - Código fuente (Next.js 14 + App Router).  
   - `README.md` con instrucciones de instalación y endpoints de la API.  
2. **PDF de ejemplo** generado desde la aplicación.  


---
