# Diseño de Infraestructura de Red Intercontinental - Evento Mundial

## 📝 Descripción del Proyecto
Este proyecto consiste en el diseño e implementación de una topología de red de gran escala (WAN/LAN) para interconectar estadios y sedes distribuidas en múltiples países (Canadá, USA y México) con un nodo central (Router Mundial). El objetivo principal fue garantizar conectividad total, redundancia lógica y distribución eficiente del tráfico internacional bajo restricciones estrictas de direccionamiento.

---

## 🛠️ Tecnologías y Protocolos Utilizados
* **Simulador:** Cisco Packet Tracer.
* **Direccionamiento IP:** Esquema Classless estricto utilizando **FLSM con máscara /14** , optimizando el espacio de direccionamiento global.
* **Enrutamiento Dinámico:** Protocolo **OSPF (Área 0)** global para la convergencia automática de rutas WAN y LAN mediante el algoritmo de Dijkstra.
* **Conmutación (Capa 2):** Implementación de Switches Core y de Acceso en cascada, configuración de **VLANs** por departamento (Servidores, Logística, Deportistas, Público) y enlaces troncales **802.1Q (Trunking)**.
* **Servicios de Red:** Enrutamiento Inter-VLAN (Router-on-a-Stick), Servidor **DNS** (Registros tipo A) y servidor **HTTP/HTTPS** para la plataforma web del evento (`www.mundial.com`).

---

## 🗺️ Arquitectura de la Red (Topología)
* **Router Mundial (Backbone Central)**
* **Red Troncal Canadá:** 
* **Red Troncal USA:**
* **Red Troncal México:** 

<img width="2334" height="775" alt="image" src="https://github.com/user-attachments/assets/77c7dc99-42e1-4312-a7ee-0a3ae699ec8d" />

---

## 🔬 Pruebas de Conectividad y Verificación
Para certificar el correcto funcionamiento del sistema, se realizaron las siguientes pruebas exitosas:
1. **Verificación de OSPF:** Comprobación de la tabla de enrutamiento global en el Router Mundial , verificando la adyacencia y el aprendizaje de todas las subredes remotas.
2. **Resolución DNS y Acceso Web:** Simulación interactiva desde terminales de usuarios en estadios remotos de México y USA, ejecutando `nslookup www.mundial.com` y cargando con éxito la página web del torneo alojada en el servidor web de Vancouver.
3. **Pruebas de Capa 3 (ICMP):** Trazas de paquetes de punta a punta demostrando la correcta configuración de Default Gateways y subinterfaces en toda la infraestructura.
