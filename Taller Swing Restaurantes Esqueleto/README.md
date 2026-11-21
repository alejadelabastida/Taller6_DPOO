# Taller 6 – GUIs con Swing y Java2D

## Cómo ejecutar
**Eclipse:** 
1. `File > Import > General > Existing Projects into Workspace`.
2. En *Select root directory* elegir la carpeta del proyecto (la que contiene `src` e `imagenes`) y pulsar *Finish*.
3. Clic derecho sobre `src/uniandes/dpoo/swing/interfaz/principal/VentanaPrincipal.java` > `Run As > Java Application`

## Cómo usar la aplicación
1. **Ventana principal:** lista de restaurantes. Al seleccionar uno se ven su nombre, su calificación (estrellas) y si fue visitado.
2. **Nuevo:** abre la ventana para agregar un restaurante. Se escribe el nombre (obligatorio), se elige la calificación (1 a 5) y si fue visitado, y se hace clic sobre el mapa para marcar su ubicación (punto rojo). *Crear restaurante* lo agrega a la lista; *Cerrar* cancela.
3. **Ver todos:** abre el mapa, donde se dibujan con Java2D el punto y el nombre de cada restaurante. Los radio buttons permiten ver **Todos** o solo los **Visitados**

## Diseño (diagrama de clases)
- **Superclases:** las ventanas extienden `JFrame` y los paneles extienden `JPanel`.
- **Interfaces:** `ActionListener` (`PanelBotones`, `PanelBotonesAgregar`, `VentanaMapa`), `MouseListener` (`PanelMapaAgregar`), `ListSelectionListener` (`PanelLista`).
- **Widgets:** cada panel/ventana se asocia por composición con los widgets Swing que contiene (`JButton`, `JList`, `JLabel`, `JCheckBox`, `JTextField`, `JComboBox`, `JRadioButton`).
- **Separación GUI / lógica:** `VentanaPrincipal` se asocia con `Diario` (atributo `mundo`), que contiene los `Restaurante`. El resto de la interfaz accede a la lógica a través de `VentanaPrincipal`.
- **Colaboraciones:** cada panel conoce a su ventana (`ventanaPrincipal`) para notificarle los eventos; `VentanaPrincipal` crea y coordina las demás ventanas y paneles.