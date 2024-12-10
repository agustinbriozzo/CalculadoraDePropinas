# Calculadora de Propinas y Consumos

Una aplicación interactiva que permite gestionar consumos y calcular propinas de forma sencilla.

## Demo

Puedes probar la aplicación aquí: [Calculadora de Propinas y Consumos](https://calculadora-propinas-agustin.netlify.app/)

## Características

- **Menú interactivo**: En el lado izquierdo, se muestra un menú con una lista de comidas y sus precios.
- **Gestión de consumos**: Al seleccionar una comida, esta se agrega automáticamente al área de consumos en el lado derecho, mostrando:
  - La cantidad consumida de cada comida.
  - El precio actualizado según la cantidad.
- **Cálculo de propinas**: Selecciona un porcentaje de propina (10%, 20%, o 50%) y observa el desglose en tiempo real.
- **Resumen detallado**: Muestra el subtotal, la propina calculada y el total a pagar.
- **Botón "Guardar orden"**: Actualmente borra la orden existente, pero está preparado para futuras expansiones.
- **Estilo moderno**: Diseño minimalista y funcional utilizando Tailwind CSS.

## Tecnologías utilizadas

- Vite
- React
- TypeScript
- Tailwind CSS

## Hook `useOrder`

El hook `useOrder` gestiona la lógica central de la aplicación, incluyendo:

- **Gestión de pedidos**:
  - Agregar comidas al pedido, actualizando la cantidad si ya están presentes.
  - Eliminar comidas del pedido.
  - Limpiar el pedido y restablecer la propina con `placeOrder`.
- **Gestión de propinas**: Permite ajustar el porcentaje de propina.
- **Estado reactivo**: Utiliza `useState` para manejar el estado de los pedidos y las propinas.

### Funciones del hook

- **`addItem(item: MenuItem)`**: Agrega un artículo al pedido. Si ya existe, incrementa su cantidad.
- **`removeItem(id: MenuItem["id"])`**: Elimina un artículo del pedido por su ID.
- **`placeOrder()`**: Limpia el pedido y reinicia el porcentaje de propina.
- **`setTip(value: number)`**: Ajusta manualmente el porcentaje de propina.
- **`order`**: Lista de artículos del pedido.
- **`tip`**: Porcentaje de propina seleccionado.

### Ejemplo de uso

```typescript
const { order, tip, setTip, addItem, removeItem, placeOrder } = useOrder();

// Agregar un artículo al pedido
addItem({ id: 1, name: "Pizza", price: 12 });

// Eliminar un artículo del pedido
removeItem(1);

// Ajustar la propina
setTip(20);

// Finalizar el pedido
placeOrder();
```
