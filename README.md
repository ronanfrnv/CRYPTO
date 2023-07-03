# CRYPTO

## Partie 1 : OpenSSL

Chiffrer un ficher (avec encodage rc4 et mdp : motdepasse)
```
openssl enc -rc4 -in texte.txt -out crypt.dat -pass pass:motdepasse
```

Déchiffrer ce même message (il faut savoir l'encodage et mdp utilisé) -> Le -d signifie décodage
```
openssl enc -d -rc4 -in crypt.dat -k motdepasse
```


Chiffrer avec Blow Fish (en ajoutant de l'aléatoire = iv + une clé = K) Le iv doit faire 16 caractères
```
openssl enc -bf-cbc -in texte.txt -out clair1.bf_cbc -K 0123456789ABCDEF0123456789ABCDEF -iv 0123456789ABCDEF
```

Déchiffrre ce même message
```
openssl enc -bf-cbc -d -in clair1.bf_cbc -out test.txt -iv 0123456789ABCDEF -K 0123456789ABCDEF0123456789ABCDEF
```

Créer une chaine de 128 bits encodé en base 64
```
openssl rad -base64 128
```

Chiffre en aes-256-cbc et encode en base64 -> plus safe
```
openssl enc -aes-256-cbc -in text.txt -a  -out fich1.base64
```

Hacher un fichier (pour hacher, on utilise la fonction dgst)
```
openssl dgst -sha256 texte.txt > texte.hash
```

Générer une clé asymétrique
```
openssl genrsa -out jspit.pem 2048
```

En extraire la clé publique 
```
openssl rsa -pubout -in bastien.pem -out bastien_pub.pem
```

Chiffre avec un clé publique
```
openssl rsautl -encrypt -in pour_bob.txt --pubin Bob.pub -out sortie_bob
```

Déchiffrer un document avec une clé privée (document qui avait été chiffré avec la clé publique)
```
openssl rsautl -decrypt -in fich_Bob_Pub -inkey Bob.pem -out sortie_bob
```
