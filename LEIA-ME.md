# Checklist de Campo SIMIL – MAHESA · Guia de instalação

## Arquivos desta pasta (suba todos no GitHub)
index.html · sw.js · manifest.webmanifest · icon-180.png · icon-512.png

## Regras do Firestore (Firebase → Firestore Database → Regras)
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid}/{document=**} {
      allow read, write: if request.auth != null && request.auth.uid == uid;
    }
  }
}
```

## Publicar versão nova
1. Substitua o index.html no GitHub (Add file → Upload files → Commit).
2. Em sw.js, troque `simil-v2` por `simil-v3` (e assim por diante) e suba também.
3. Cada aparelho atualiza sozinho na próxima abertura com internet.
