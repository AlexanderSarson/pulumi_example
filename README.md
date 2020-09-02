# pulumi_example

1. Opret en konto på https://www.pulumi.com og generate en Access Token. Gem denne til når kommando'en 'pulumi up' skal bruges.
2. Opret en konto på https://www.digitalocean.com og generate en Access Token. Gem denne til, når config skal sættes op.
3. Git clone dette repo lokalt.
4. Åben folderen i VS Code og vælg at reopen i container. Vent til installation af containeren er færdig.
5. Kør ssh-keygen -t rsa -m PEM -f ssh/id_rsa fra terminalen i containeren. Tjek at de 2 nøgler er blevet oprettet i .ssh folderen (Man kan også bruge sine egne, men de skal være med PEM. Kør eventuelt 'ssh-keygen -m PEM -t id_rsa' på en eksisterende nøgle).
6. kør 'pulumi config set domain YOURDOMAIN' i containeren.
7. kør 'pulumi config set digitalocean:token XXXXXXXXXXXXXX --secret' i containeren.
8. kør 'pulumi up' og indtast pulumi access token. Sig ja til at der skal rettes en stack osv, Sig ja til at den skal perform en update. vent til den er færdig.
9. Man kan nu bruge ssh til at logge ind i dropletten. 'ssh root@IP'.
10. kør 'pulumi destroy' for at fjerne alt igen.

a. Hvis den fejler et trin, så kør 'pulumi up' igen og den vil fortsætte, hvor den slap.

b. Hvis man bliver nødt til at afbryde den imens den er igang og den brokker sig over 'pending operation', så kør 'pulumi stack export | pulumi stack import' og prøv igen.
