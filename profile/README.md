# Edufy Projects
## _"We server you media"_
---
## 🎧 Overview
These are back-end projects that serves to handel media of the type of songs, album, podcasts and videos. With it we want to make media more accessible. 
Different media types can be worked with alone, one dose not need to have all. Though, if less than all three, the docker and sql file will be required to changed to only include 
the chosen media services. The front-end will be added later by another team

---
## 🧩 Related projects
### Organisation
- [EdufyProjects](https://github.com/EudfyProjects) - All repositories in one place
### Connections
- [Edify-infra](https://github.com/EudfyProjects/Edufy-infra) - Contains `docker-compose.yml` file and `init.db` file
- [EudfyEurekaServer](https://github.com/Sommar-skog/EdufyEurekaServer) - Server that connects the services instances
- [Gateway](https://github.com/SaraSnail/EdufyGateway) - Funnels all requests with one base endpoint
- [EdufyUser](https://github.com/Jamtgard/EdufyUser) - Holds in the Users and can connect to Keycloak to create new ones
- [EdufyKeycloak](https://github.com/Sommar-skog/EdufyKeycloak) - A pipeline for Azure but had to switch to local container 
### Media connections
- [EdufyCreator](https://github.com/Sommar-skog/EdufyCreator) - Holds the Creators for all the media services
- [EdufyGenre](https://github.com/a-westerberg/EdufyGenre) - Holds all the Genres for the microservices
- [EdufyThumb](https://github.com/a-westerberg/EdufyThumb) - Records of thumbs up and down on media
- [EdufyUtility](https://github.com/a-westerberg/EdufyUtility) - No code so far but was created to hold algorithms to extract top 10 for a User
### Media services
- [EdufyPod](https://github.com/SaraSnail/EdufyPod) - Service for podcast episodes and seasons
- [EdufyMusic](https://github.com/Jamtgard/EdufyMusic) - Service for songs and albums
- [EdufyVideo](https://github.com/Sommar-skog/EdufyVideo) - Service for video clips and video playlists

---
## 🏁 Getting started
### Prerequisites

- Java 21
- Maven
- Docker 
- Postman
- Keycloak
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
- Use `docker-compose.yml` to build and run the project, how and files are in [Edufy-infra](https://github.com/EudfyProjects/Edufy-infra)
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
- File and placement is in [Edufy-infra](https://github.com/EudfyProjects/Edufy-infra)
