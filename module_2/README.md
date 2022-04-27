# Rezultāti ir sekojoši:

$ git log module_1/2.jpg
commit 2ba62e8c5245fbc555387a91b1b0a81d4653da79
Author: OskarsZile <oskars@itnt.lv>
Date:   Wed Apr 27 11:51:24 2022 +0300

    pievienoju pirmo versiju

AzureAD+oskars@PC-412 MINGW64 ~/git_repos/OskarsZile (main)
$ git log module_2/2.jpg
commit 8989b2f221be757e0f92f27c5351811a3584205c (HEAD -> main, origin/main, origin/HEAD)
Author: OskarsZile <oskars@itnt.lv>
Date:   Wed Apr 27 12:13:13 2022 +0300

    Pievienoju module2

AzureAD+oskars@PC-412 MINGW64 ~/git_repos/OskarsZile (main)
$ git log module_1/3.jpg
commit 2ba62e8c5245fbc555387a91b1b0a81d4653da79
Author: OskarsZile <oskars@itnt.lv>
Date:   Wed Apr 27 11:51:24 2022 +0300

    pievienoju pirmo versiju

AzureAD+oskars@PC-412 MINGW64 ~/git_repos/OskarsZile (main)
$ git log module_2/3.jpg
commit 8989b2f221be757e0f92f27c5351811a3584205c (HEAD -> main, origin/main, origin/HEAD)
Author: OskarsZile <oskars@itnt.lv>
Date:   Wed Apr 27 12:13:13 2022 +0300

    Pievienoju module2



## Secinājums:

### Commitu HASH atšķiras, jo tie ir nevis failu HASH bet konkrēto darbību, jeb commitu, faili ir identiski un tiem būtu jābūt vienādiem HASH vērtībām.


***

### 16. Pārbaudīt kādas izmaiņas tika veiktas iepriekšējās nedēļas laikā. Atrast vismaz divus veidus kā to izdarīt.

git log --since=2.weeks
git log --after="2022-04-17" --before="2022-04-25" 

### 17. Atrast commit kurus veica autors - “Laura Pacilio”

git log | grep "Laura" -A5 -B5

Laura kopā veikusi 450 commitus;

### 18. Atrast vai Laura ir veikusi commit pagājušā gada septembrī?

git log --after="2021-08-31" --before="2021-10-01" | grep "Laura Pacilio" -c

Iegūsim skaitu cik izmaiņas bijušas;

git log --after="2021-08-31" --before="2021-10-01" | grep "Laura Pacilio" -A10 -B 10 --color

Iegūsim izmaiņu detaļas;

### 19. Vai Laura ir veikusi commit vakar?

git log -n 10, redzams, ka nav Lauras commitu;

Atbilde:Nē

***


### * Atlasot rezultātus no pagājušā gada 20 līdz 21 aprīlim var atrast commit kurš ir datēts ar 16 aprīli? Kāpēc tā ir? Atbildi apkopot module_2 > README.md un pārsūtīt rezultātu Github.

Jā tā tiešām ir ja meklējam ar: git log --after="2021-04-20" --before="2021-04-22"

commit f8493bf5cd78bc2a723f5ddc6f6bceb0e08813ea
Author: James Bardin <j.bardin@gmail.com>
Date:   Fri Apr 16 17:11:27 2021 -0400

    update hcl

    update to v2.10.0

Taču ja skatamies izmantojot web pārlūku, ir korekts datums 21.04.2022

https://github.com/hashicorp/terraform/commits/main?after=e217c0c53a5b8706de31dea1bcf7e673ec638a24+1714&branch=main

Iemeslu nezinu, iespējams, datuma formāts nepareizi attēlots?


