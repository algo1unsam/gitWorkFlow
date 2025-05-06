# Flujo de trabajo con Git y ramas

##  Clonar el repositorio

```bash
git clone <URL-del-repositorio>
```

---

##  Crear ramas y subirlas al remoto

### Crear y subir `rama1`:

```bash
git checkout -b rama1
git add .
git commit -m "Cambios en rama1"
git push --set-upstream origin rama1
```

### Crear y subir `rama2`:

```bash
git checkout -b rama2
git add .
git commit -m "Cambios en rama2"
git push --set-upstream origin rama2
```

---

##  Traer cambios desde `main` hacia una rama

### En cualquier rama (por ejemplo, en `rama2`):

```bash
git fetch origin
git merge origin/main
```

>  **Si hay conflictos:** resolvelos, luego:

```bash
git add .
git commit
git push
```

---

##  Actualizar `main` desde remoto y hacer merge de una rama

### Ir a `main` y actualizar desde remoto:

```bash
git checkout main
git pull origin main
```

### Hacer merge de una rama (por ejemplo, `rama1`) a `main`:

```bash
git merge rama1
git push
```

---

##  Hacer merge de otra rama (`rama2`) a `main`

### Desde `rama2`, traer cambios de `main`:

```bash
git checkout rama2
git fetch origin
git merge origin/main
```

>  **Si hay conflictos:** resolvelos, luego:

```bash
git add .
git commit
git push
```

### Volver a `main`, actualizar y hacer merge de `rama2`:

```bash
git checkout main
git pull origin main
git merge rama2
git add .
git commit
git push origin main
```
