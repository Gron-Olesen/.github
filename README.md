# 🛠 Arbejdsguide – Grøn & Olesen Eksamen (GitHub Projects + Branches)

Denne guide hjælper dig og teamet med at holde styr på workflow, navngivning og hvordan man arbejder med vores GitHub Project board og repositories.

---

## 🔧 Sådan bruger vi **GitHub Projects**

- Vi har **én kolonne per microservice** i boardet – så vi hurtigt ser hvem der arbejder hvor
- Hver opgave laves som et **GitHub Issue**
- Issues er navngivet med `[Service] #ID – Beskrivelse`  
  Eksempel: `AuthService #3 – Tilføj JWT-validering`

---

## ✍️ Sådan opretter du et nyt Issue

1. Gå til vores [Project board](https://github.com/orgs/Gron-Olesen/projects)
2. Vælg den rigtige kolonne (fx “ProfileService”)
3. Tryk på `+ Add item`
4. Skriv en kort og konkret titel på opgaven

Eksempler:
- `CatalogService #5 – Slet vare`
- `Infrastructure #10 – Dockerfile til profile-service`

---

## 🌱 Branch-struktur

### Sådan navngiver vi branches:

| Type        | Format                       | Eksempel                         |
|-------------|------------------------------|----------------------------------|
| Feature     | `feature/<navn>`             | `feature/login-endpoint`         |
| Refactor    | `refactor/<hvad>`            | `refactor/jwt-service`           |
| Bugfix      | `fix/<hvad>`                 | `fix/jwt-token-expiry`           |
| Infrastruktur | `infra/<hvad>`             | `infra/vault-seed`               |
| Test        | `test/<hvad>`                | `test/auth-login-flow`           |

---

## 🧪 Sådan kobler du branch til issue

1. Når du starter på et issue (fx `#3`), opret en branch:
   ```bash
   git checkout -b feature/login-endpoint
   ```

2. Når du committer, referér til issue med `closes`:
   ```bash
   git commit -m "Implementer login-endpoint (closes #3)"
   ```

3. Når du laver pull request og merger til `main`, lukkes issue #3 automatisk ✅

---

## ✅ Når du er færdig med en opgave

1. Lav `git push origin <din-branch>`
2. Lav Pull Request mod `main` (eller merge selv hvis det er trygt)
3. Luk evt. issue manuelt hvis det ikke blev koblet med `closes #`

---

## 🔁 Bonus: Hurtige kommandoer

```bash
# Opret ny branch til ny feature
git checkout -b feature/opret-login-endpoint

# Push din branch til GitHub
git push origin feature/opret-login-endpoint

# Skift tilbage til main
git checkout main

# Hent nyeste kode fra main
git pull
```

---

## 📘 Ekstra tips

- Skriv små commits – gør det nemt at se hvad der er lavet
- Arbejd kun på **én feature per branch**
- Test altid din kode lokalt inden du merger til main
- Husk `docker compose down -v` sletter al data (MongoDB m.m.)

---

God arbejdslyst 🚀
