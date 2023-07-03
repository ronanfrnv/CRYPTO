Voici une reformulation des commandes pour utiliser OpenSSL dans différentes opérations de chiffrement et de hachage :

1. Chiffrer un fichier en utilisant l'algorithme RC4 avec un mot de passe :
```
openssl enc -rc4 -in texte.txt -out crypt.dat -pass pass:motdepasse
```

2. Déchiffrer un fichier chiffré avec l'algorithme RC4 en utilisant le même mot de passe :
```
openssl enc -d -rc4 -in crypt.dat -out texte_dechiffre.txt -pass pass:motdepasse
```

3. Chiffrer un fichier en utilisant l'algorithme Blowfish avec un vecteur d'initialisation (IV) et une clé :
```
openssl enc -bf-cbc -in texte.txt -out chiffre.bf_cbc -K 0123456789ABCDEF0123456789ABCDEF -iv 0123456789ABCDEF
```

4. Déchiffrer un fichier chiffré avec l'algorithme Blowfish en utilisant le même IV et la même clé :
```
openssl enc -bf-cbc -d -in chiffre.bf_cbc -out texte_dechiffre.txt -iv 0123456789ABCDEF -K 0123456789ABCDEF0123456789ABCDEF
```

5. Générer une chaîne de 128 bits encodée en base64 :
```
openssl rand -base64 128
```

6. Chiffrer un fichier en utilisant l'algorithme AES-256-CBC et encoder le résultat en base64 :
```
openssl enc -aes-256-cbc -in texte.txt -a -out chiffre.base64
```

7. Hacher un fichier en utilisant l'algorithme de hachage SHA-256 :
```
openssl dgst -sha256 texte.txt > texte.hash
```

8. Générer une paire de clés asymétriques :
```
openssl genrsa -out cle_privee.pem 2048
```

9. Extraire la clé publique à partir de la clé privée :
```
openssl rsa -pubout -in cle_privee.pem -out cle_publique.pem
```

10. Chiffrer un fichier en utilisant la clé publique :
```
openssl rsautl -encrypt -in texte.txt -pubin -inkey cle_publique.pem -out chiffre_rsa.txt
```

11. Déchiffrer un fichier chiffré avec la clé publique en utilisant la clé privée correspondante :
```
openssl rsautl -decrypt -in chiffre_rsa.txt -inkey cle_privee.pem -out texte_dechiffre.txt
```

Assurez-vous d'adapter ces commandes en fonction de votre système d'exploitation et des chemins d'accès aux fichiers nécessaires.
