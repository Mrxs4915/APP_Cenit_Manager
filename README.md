# CENIT MANAGER

PROYECTO: CENIT MANAGER

Descripción general

Desarrollar una aplicación web profesional llamada CENIT Manager.

La aplicación debe servir como una plataforma modular para gestión profesional de proyectos, clientes, cotizaciones, horas trabajadas, viáticos, kilometraje, informes técnicos y control financiero.

La plataforma debe ser escalable y permitir agregar nuevos módulos sin modificar el núcleo del sistema.

STACK TECNOLÓGICO
Frontend
- React 18
- Vite
- React Router DOM
- Context API
- Tailwind CSS
- React Hook Form
- Lucide React Icons

Backend
- Node.js
- Express
- PostgreSQL
- Prisma ORM

Extras
- JWT Authentication
- Exportación PDF
- Exportación Excel
- Responsive Design
- Dark Mode (preparado para el futuro)

ARQUITECTURA

Implementar arquitectura modular.

src/
│
├── components/
│   ├── Sidebar.jsx
│   ├── Navbar.jsx
│   ├── DashboardCards.jsx
│   └── ModuleLoader.jsx
│
├── modules/
│   ├── dashboard/
│   ├── proyectosPropios/
│   ├── proyectosEmpresa/
│   └── ingresos/
│
├── pages/
│
├── hooks/
│
├── context/
│
├── services/
│
├── utils/
│
├── config/
│
└── App.jsx

MÓDULO CORE

Implementar:

Dashboard General

Mostrar:

- Facturación mensual
- Cobrado
- Pendiente de cobro
- Horas trabajadas
- Kilómetros recorridos
- Cantidad de proyectos activos
- Próximos cobros
- Menú lateral dinámico

Los módulos deben cargarse desde:

configModules.js

Ejemplo:

export const MODULES = [
  {
    id: "dashboard",
    name: "Dashboard"
  },
  {
    id: "proyectosPropios",
    name: "Proyectos Propios"
  },
  {
    id: "proyectosEmpresa",
    name: "Proyectos Empresa"
  },
  {
    id: "ingresos",
    name: "Ingresos"
  }
];

MÓDULO: PROYECTOS PROPIOS

Este módulo corresponde a la actividad profesional independiente.

Debe incluir
Clientes

Campos:

- Nombre
- Teléfono
- Correo
- Dirección
- Observaciones


Operaciones:

- Crear
- Editar
- Eliminar
- Buscar
Cotizaciones

Campos:

- Número consecutivo
- Fecha
- Cliente
- Lugar
- Tipo
- Descripción
- Cantidad
- Precio unitario
- Descuento
- IVA
- Subtotal
- Total
- Estado


Estados:

- Pendiente
- Aprobada
- Rechazada
- Cobrada


Funciones:

- Crear cotización
- Editar
- Duplicar
- PDF
- Convertir a proyecto
Proyectos

Campos:

- Número
- Cliente
- Nombre
- Presupuesto
- Estado
- Fecha inicio
- Fecha final
- Notas


Estados:

- Pendiente
- Activo
- En espera
- Finalizado
- Cancelado


Funciones:

- Crear proyecto
- Convertir cotización en proyecto
- Registrar gastos
- Registrar ingresos
- Calcular utilidad
Gastos

Campos:

- Fecha
- Proyecto
- Categoría
- Descripción
- Monto

Ingresos

Campos:

- Fecha
- Proyecto
- Descripción
- Monto

MÓDULO: PROYECTOS EMPRESA

Este módulo corresponde a trabajos realizados para otras empresas.

Actualmente representado por HGT.

Registro de Jornadas

Campos:

- Fecha
- Proyecto
- Lugar
- Cliente
- Modalidad
- Horas trabajadas


Modalidad:

- Campo
- Gabinete

Kilometraje

Campos:

- Vehículo
- Kilometraje Inicial
- Kilometraje Final
- Tarifa por km


El sistema debe calcular:

- Kilómetros recorridos
- Monto kilometraje


Automáticamente.

Viáticos

Tipos:

- Desayuno
- Almuerzo
- Cena
- Hospedaje
- Peajes
- Parqueos
- Otros


Campos:

- Tipo
- Monto
- Factura
- Observaciones

Liquidación

Calcular:

Horas trabajadas × tarifa hora

+
Kilometraje

+
Viáticos

Mostrar:

- Total por jornada
- Total mensual
- Total anual

MÓDULO: INGRESOS

Representa trabajos realizados para terceros similares a VALCO.

Registro de actividades

Tipos:

- Informe
- Lámina
- Otro


Campos:

- Fecha
- Cliente
- Proyecto
- Tipo
- Descripción
- Monto
- Estado


Estados:

- Pendiente
- Cobrado

Indicadores

Mostrar:

- Total facturado
- Total cobrado
- Pendiente
- Cantidad de informes
- Cantidad de láminas

GESTIÓN DE VEHÍCULOS

Permitir múltiples vehículos.

Campos:

- Nombre
- Año
- Combustible
- Cilindraje
- Tipo
- Tarifa manual opcional


Tipos:

- Rural gasolina
- Rural diésel
- Liviano A
- Liviano B
- Liviano diésel
- Motocicleta gasolina
- Motocicleta eléctrica
- Vehículo híbrido
- Vehículo eléctrico


El sistema debe calcular automáticamente la tarifa de kilometraje según el tarifario configurado.

CONFIGURACIÓN DEL USUARIO

Campos:

- Nombre profesional
- Correo
- Teléfono
- IVA por defecto
- Cuentas bancarias
- Términos y condiciones
- Logo
- Firma

BASE DE DATOS

Crear modelos Prisma para:

- User
- Client
- Quote
- Project
- Expense
- Income
- Vehicle
- WorkSession
- TravelExpense
- Report
- Module


Agregar relaciones completas.

REQUISITOS DE UI
- Diseño limpio profesional
- Responsive
- Sidebar colapsable
- Dashboard moderno
- Tablas con filtros
- Formularios reutilizables
- Confirmaciones de eliminación
- Loading states
- Empty states
- Toast notifications

REQUISITOS DE CÓDIGO
- Componentes reutilizables
- Hooks personalizados
- Servicios separados
- Código tipado con JSDoc
- Buenas prácticas React
- Arquitectura escalable
- Preparado para producción

Genera el proyecto completo siguiendo esta especificación, creando la estructura de carpetas, componentes, páginas, rutas, modelos de base de datos, servicios y vistas principales. Basar la lógica del negocio en un sistema modular donde cada módulo sea independiente y pueda activarse o desactivarse desde la configuración.
