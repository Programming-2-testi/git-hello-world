# Git "Hello world"

Tässä tehtävässä opit perusasioita Git-versionhallinnasta. Tehtävän edellytyksenä on, että olet asentanut Git-työkalun koneellesi ja tehnyt tarvittavat asetukset Gitin käyttämiseksi: [Set up Git (GitHub)](https://docs.github.com/en/get-started/quickstart/set-up-git). Tarvitset myös [GitHub](https://github.com/)-tunnuksen<sup>1</sup>, jonka voit luoda osoitteessa https://github.com/.

<sup>1</sup> <em>Jos käytät GitHubia jo valmiiksi työsi puolesta, voi olla tietoturvasyistä kannattavaa luoda erillinen tunnus opintoja varten.</em>

🔐 *Sinun ei tarvitse antaa omaa nimeäsi GitHub-rekisteröitymisessä. Sähköpostiosoitteena voit käyttää oppilaitoksen sähköpostia ja voit piilottaa sen muilta käyttäjiltä seuraamalla [GitHubin ohjeita](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address#setting-your-commit-email-address-on-github).*


## Git-komentorivityökalu

Tehtävänanto keskittyy Git-komentorivityökaluun. Itse komentorivin osalta oletamme komentorivin peruskäytön, kuten komentorivin avaamisen ja eri hakemistojen välillä siirtymisen, olevan ennalta tuttua. Mikäli komentorivi aiheuttaa ongelmia, tämän ja seuraavat tehtävät voi ratkaista myös graafisella työkalulla, kuten VS Code tai GitHub desktop:

* [Using Git source control in VS Code ](https://code.visualstudio.com/docs/sourcecontrol/overview)
* [GitHub Desktop](https://desktop.github.com/)

Kurssin ohjeistuksessa oletetaan, että käytät komentorivityökalua, joten joudut etsimään vastaavat toiminnot omasta työkalustasi itsenäisesti.


## Gitin perusteet

Git on erittäin monipuolinen työkalu ja sen käyttämiseksi löytyy valtava määrä erilaisia ohjeita ja tutoriaaleja. Tutoriaalien näkökulma ja sisältö vaihtelee melko suuresti jo Gitin perusteiden osalta: osassa luodaan itse oma repositorio, osassa kloonataan valmis repositorio. Osassa luodaan ja yhdistellään kehityshaaroja, kun taas toisissa työskennellään vain yhdessä kehityshaarassa.

Tässä tehtävässä tarvitset vain Gitin komentoja `clone`, `add`, `commit` ja `push`. Kaikki syventävämmät aiheet, esimerkiksi kehityshaaroihin (branch) liittyen, voit jättää ainakin toistaiseksi väliin.


## Tehtävä

Tässä tehtävässä tarkoituksesi on ladata tämä Git-repositorio omalle koneellesi, tehdä siihen pieni muutos, ja päivittää tekemäsi muutos takaisin etärepositorioon.


### Repositorion kloonaaminen

Aloita kloonaamalla tämä Git-repositorio omalle koneellesi. Harjoitus täytyy tehdä omassa kopiossasi, eli varmista, että repositorion osoitteessa on mukana oma GitHub-käyttäjätunnuksesi! Tarkemmat ohjeet oman kopion luomiseksi löydät oman kurssitoteutuksesi ohjeista:

```sh
git clone https://github.com/varmista-etta-github-tunnuksesi-on-repositorion-osoitteessa.git
```

Kun olet kloonannut repositorion tietokoneellesi valitsemaasi hakemistoon, avaa hakemisto koodieditorillasi.


### Tiedoston muokkaaminen

Avaa repositoriossa valmiiksi oleva tiedosto [hello.txt](./hello.txt) koodieditorilla. Lisää tiedostoon teksti `hello world` ja tallenna tiedosto.

Käytä `git status` -komentoa ja tarkastele sen tulostetta. Näkyykö `hello.txt` tulosteessa? Mitä siitä kerrotaan?


### Muutoksen lisääminen

Tekemäsi muutos `hello.txt`-tiedostoon täytyy seuraavaksi lisätä osaksi commit:ia. `git status`-komento tunnistaa, että tiedosto on muuttunut, ja näyttää vinkin tarvitsemastasi komennosta muutoksen lisäämiseksi versionhallintaan:

```sh
git status
git *** hello.txt    # korvaa *** edellisen komennon antamalla ohjeella
```

Yhdessä commitissa voidaan muuttaa useampia tiedostoja, jolloin voisit jatkaa tiedostojen lisäämistä samaan committiin. Tällä kertaa meille riittää tämä yksi tiedosto.


### "Commitin" luonti

Kun suoritat `git status`-komennon, Git näyttää, mitkä tiedostot ovat valmiina commitoitavaksi:

```sh
git status
```

```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   hello.txt
```

Käytä seuraavaksi `git commit` -komentoa, joka luo uuden commitin, jossa tekemäsi muutos on mukana:

```sh
git commit -m "Hello world lisätty tiedostoon"
```

`-m` tarkoittaa ns. "commit messagea", eli viestiä, jolla tämä muutos tunnistetaan versiohistoriassa myöhemmin.


### Commitin vienti etärepositorioon

Aja commitin luonnin jälkeen tuttu komento:

```sh
git status
```

Nyt Git kertoo, että paikallinen kopiosi repositoriosta on yhden commitin edellä etärepositoriota:

```
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git ****" to publish your local commits)
```

Noudata Gitin antamaa ohjetta ja anna komento, jolla julkaiset paikalliset muutoksesi etärepositorioon:

```sh
git ****    # korvaa **** edellisestä komennosta saamallasi ohjeella
```

Käy lopuksi tarkastamassa etärepositoriosi sisältö. Onko `hello.txt` päivittynyt?


## .gitignore ja .gitattributes

Tämä pohja sisältää myös valmiiksi määritellyt [`.gitignore`](./.gitignore)- ja [`.gitattributes`](./.gitattributes)-tiedostot. `.gitignore`:ssa on määritelty, mitkä tiedostot jätetään [versionhallinnan ulkopuolelle](https://git-scm.com/docs/gitignore), kun taas `.gitattributes`-tiedostossa on määritetty kaikille tekstitiedostoille [yhtenäiset rivinvaihtomerkit](https://docs.github.com/en/get-started/getting-started-with-git/configuring-git-to-handle-line-endings). Voit muokata näitä tiedostoja tarpeidesi mukaan.


⛔ *Jos et missään tapauksessa halua käyttää kurssilla GitHubia, sovi opettajasi kanssa mahdollisesta vaihtoehtoisesta palvelusta tai tehtävien palautustavasta.*

-----

Tämän tehtävän luonnissa on hyödynnetty [GhatGPT 3.5](https://chat.openai.com/) -kielimallia.


