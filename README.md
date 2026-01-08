# Development Environment con code-server

Este repositorio contiene la configuración para levantar un entorno de desarrollo **frontend y backend** usando **code-server** en un solo contenedor Docker.  
Ideal para crear un **MVP** rápidamente en tu VPS sin necesidad de instalar localmente Node, Python u otros stacks.

---

## 📝 Estructura de carpetas

```text
projects/
├─ frontend/      # Proyecto frontend (React, Vue, Angular, etc.)
├─ backend/       # Proyecto backend (Node, Python, etc.)
└─ shared/        # Opcional: librerías o archivos compartidos
docker-compose.yml
.env              # Variables de entorno (PASSWORD)
```
projects/ contiene todos tus proyectos y se monta dentro del contenedor.
docker-compose.yml configura el contenedor code-server.
.env almacena la contraseña para acceder a code-server.
## ⚙️ Variables de entorno
Crea un archivo .env en la raíz del repositorio:
```
Copia el nombre de la variable de .env-example y cambia el valor
PASSWORD=tu_contraseña_segura
```
## 🚀 Comandos útiles
### Eliminar contenedores y volúmenes
Esto detiene y elimina los contenedores, pero mantiene tu carpeta projects/.
Si quieres eliminar volúmenes también, añade -v
```
docker compose -f ./docker-compose.yml down
```
Levantar contenedores
```
docker compose -f ./docker-compose.yml --env-file .env up -d --build
```
## 💻 Uso del workspace
Dentro de code-server puedes:
- Abrir la carpeta projects como workspace principal.
- Abrir sub-carpetas frontend y backend como sub-workspaces.
- Abrir terminales independientes para frontend y backend:
```
# Terminal 1: Backend
cd backend
npm install
npm run dev

# Terminal 2: Frontend
cd frontend
npm install
npm run dev
```
## 🔧 Volúmenes y persistencia
projects/ → contiene tu código, persistente fuera del contenedor.
code-server-data → contiene configuración, extensiones y terminales guardadas de code-server.
## ⚡ Notas
Este entorno es solo para desarrollo, no está configurado para producción.
Puedes añadir más proyectos dentro de projects/ y abrirlos como sub-workspaces.
Para reiniciar code-server:
```
docker-compose restart
```
### Autor
- [Branm Aldair Pabon Villamizar](https://github.com/bpabon)
- [![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://portafilio-person-portafolio3103032-frontend-3eea11f21b7b3a6e28.gitlab.io/)
- [![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/branm-aldair-pabon-villamizar-63ab88210)
