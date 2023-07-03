# CRYPTO

Chiffrer un ficher (avec encodage rc4 et mdp : motdepasse)
```
openssl enc -rc4 -in texte.txt -out crypt.dat -pass pass:motdepasse
```

Déchiffrer ce même message (il faut savoir l'encodage et mdp utilisé) -> Le -d signifie décodage
```
openssl enc -d -rc4 -in crypt.dat -k motdepasse
```

Chiffrer avec Blow Fish (en ajoutant de l'aléatoire = iv + une clé = K)
```
openssl enc -bf-cbc -in texte.txt -out clair1.bf_cbc -K 0123456789ABCDEF0123456789ABCDEF -iv 0123456789ABCDEF
```
