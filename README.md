📦 mini-wms  
This is a microservices based Warehouse Management System Project built with Spring Boot and React . During my bachelors i worked in a ware house that used a similar software and now i decided to create my own :)

---


 Architecture : 
Services
- **Inventory Service** (port 8081) → Manages Articles, stock levels, reservations  
- **Order Service** (port 8082) → Accepts customer orders, coordinates stock reservations  
- **Inbound Service** (port 8083) → Records goods received into the warehouse  
- **Picking Service** (port 8084) → Handles allocation of pick tasks for orders  
- **Shipping Service** (port 8085) → Confirms shipments, reduces on-hand stock  
- **Billing Service** (port 8086) → Creates invoices, tracks payments  
- **Reporting Service** (port 8087) → Provides stock and order insights  
- **Gateway (optional)** (port 8080) → API entrypoint  
- **Frontend (React + Vite)** (port 5173) → UI for interaction

Architecture Overview : 


### High-level flow
1. A user places an **Order** → Order Service  
2. Order Service calls **Inventory Service** to reserve stock  
3. On success → order is (Allocated), on failure → (Rejected)  
4. Later, **Picking & Shipping** update inventory (consume reserved → shipped)  
5. **Reporting** aggregates data for dashboards to make it easier for pickers and warehouse supervisors to track the movements . 

---

🛠️ Tech Stack
- **Backend**: Java 21, Spring Boot 3, Spring Data JPA, Gradle  
- **Frontend**: React 18, Vite, TypeScript  
- **Databases**: H2 (dev), PostgreSQL (planned)  
- **CI/CD**: GitHub Actions (backend + frontend build/test)  


---

## 📂 Project Structure
