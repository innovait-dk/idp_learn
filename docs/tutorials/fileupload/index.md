# File Upload

På byte/image felter i databasen er det i UI'en muligt at lave en fil-upload-control og visning af fil/billede.

De nedenstående eksempler er lavet på Northwind's Category, som har et felt "Picture" varbinary(max).

Properties der er af typen "byte[]" får i "User Interface" som default sat showcontrol til "Image - Show" og updatecontrol til "Image - Editor".

Disse kan konfigureres til at understøtte diverse scenarier. 

Som standard kan alle fil-typer uploades.

## How to

[File Upload - Et felt (bytes)](1-field.md)

[File upload - To felter (bytes og filename) - redigere filer](2-fields.md)

[File upload - 3 felter (bytes, filename og thumbnail)](3-fields.md)

[File upload - Andre konfigurationer](other-configurations.md)
