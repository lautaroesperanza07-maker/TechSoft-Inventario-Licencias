# Flujo BPMN - Cobro y Activación de Licencias

El proceso de venta y habilitación automatizada del *Módulo de Gestión de Inventario y Licencias* se divide en dos **Pools** principales:

* **Pool 1: Cliente Externo (Pyme / Usuario):** Representa al cliente que inicia el proceso al seleccionar un plan de licencia, ingresar sus datos de facturación y efectuar el pago en la pasarela, finalizando al recibir su clave de activación por correo electrónico.
* **Pool 2: TechSoft Solutions S.A. (Sistema Integrado):** Representa la organización y su infraestructura interna, dividida en tres **Lanes** (carriles):
  1. *Sistema de Cobros y API (Automatizado):* Recibe la transacción y evalúa mediante una compuerta lógica si el pago fue aprobado (derivando al backend) o rechazado (disparando una alerta de reintento como excepción).
  2. *Servidor de Licencias (Backend):* Genera la clave encriptada, la asocia al ID del cliente, fija la fecha de vencimiento y envía las credenciales por correo.
  3. *Soporte Técnico / QA (Supervisión Humana):* Monitorea el panel de control de errores e interviene ante reclamos manuales.
