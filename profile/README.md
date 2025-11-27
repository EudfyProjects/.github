# Edufy Projects
Multiple projects that handel interactions with Media

---
## 🏁 Getting started
### Prerequisites

- Java 21
- Maven
- Docker 
- Postman
---

### 🔌 Ports
#### Connections
- **Eureka :** `8761`
- **Gateway :** `4545`
- **MySQL :** `3307`
- **User :** `8686`
- **Keycloak :** `8080`

#### Media connections
- **Creator :** `8787`
- **Genre :** `8585`
- **Thumb :** `8484`
- **Utility :** `8888`
- 
#### Media services
- **Pod :** `8282`
- **Video :** `8383`
- **Music :** `8181`

---

## 🔒 Authentication & Roles

This service uses **OAuth2** for authentication and authorization.

- **User Roles:**
    - **Admin:** Can show podcasts with id, create new podcasts
    - **User:** Can view podcasts, get by title or genre, play podcast episode

> _Note: These are not "real" users/admin. They are placeholders for production and used under development._
>
| Role                |     Username      | Password |
|---------------------|:-----------------:|:--------:|
| edufy_realm_admin   | edufy_realm_admin |  admin   |
| microservice_access |                   |    |

> Note: Unauthenticated requests will receive a `401 Unauthorized` response.

> `microservice_access` is a role that clients uses between each other to authorize access

---

## 🐳 Docker
- Use `docker-compose.yml` to build and run the project, is in [Edufy-infra](https://github.com/EudfyProjects/Edufy-infra)
- Docker network: `edufy-network`

---

## 🛢️ MySQL Database

| Name               | Username | Password |   Database    |
|--------------------|:--------:|:--------:|:-------------:|
| edufy_mysql        |   assa   |   assa   | main database |
| edufy_edufyuser_db |   assa   |   assa   |     user      |
| edufy_creator_db   |   assa   |   assa   |    creator    |
| edufy_genre_db     |   assa   |   assa   |     genre     |
| edufy_music_db     |   assa   |   assa   |     music     |
| edufy_pod_db       |   assa   |   assa   |      pod      |
| edufy_thumb_db     |   assa   |   assa   |     thumb     |
| edufy_video_db     |   assa   |   assa   |     video     |

- **Version :** 8.0 
