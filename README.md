# CRYPTO

Chiffrer un ficher (avec encodage rc4 et mdp : motdepasse)
```
openssl enc -rc4 -in texte.txt -out crypt.dat -pass pass:motdepasse
```

Déchiffrer ce même message (il faut savoir l'encodage et mdp utilisé)
```
openssl enc -d -rc4 -in crypt.dat -k motdepasse
```
