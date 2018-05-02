Viikot pyörivät ja kesä tulee täysilla, vappukin oli välissä. Oliko hyvä vappu?
Sää oli mukavat +15 ja aurinkoista 8)

Nyt mennään tehtäviin kuitenkin. Päästään kokeilemaan vähän git:iä.


### Tehtävät löytyvät kurssin sivulta - [Terokarvinen.com Palvelinten-Hallinta](terokarvinen.com/2018/aikataulu-%e2%80%93-palvelinten-hallinta-ict4tn022-4-ti-5-ke-5-loppukevat-2018-5p)
Tässä harjoituksessa luodaan git:n avulla sls tila, mikä cloonataan [GitHubista](http://github.com) ja ajetaan sen jälkeen bash komennolla.
Joten salt-masteria ei välttämättä tässä tarvita, ellei haluta ajaa tämä tila sen kautta.


Käytän testi koneessa [xubuntu-16.04.4-desktop-amd64.iso](http://ftp.lysator.liu.se/ubuntu-dvd/xubuntu/releases/16.04/release/xubuntu-16.04.4-desktop-amd64.iso), mikä on ajettu usbtikulle [UNetBootilla](https://unetbootin.github.io/)


## Tehtävät
## h5
Poikkeuksellisesti pidempi palautusaika w18 perjantaina 2018-05-04 12:00 asti. Vappupäivänä ei ole opetusta. Hauskaa Wappua!

a) Valitse aihe omaksi kurssityöksi ja varaa se kommenttina aikataulusivun perään.

b) Julkaise raportti MarkDownilla. Jos käytät GitHub:ia, se tekee muotoilun automaattisesti “.md”-päätteisiin dokumentteihin.

c) Aja oma Salt-tila suoraa git-varastosta. Voit joko tehdä tilan alusta lähtien itse tai forkata [sirottimen](https://github.com/terokarvinen/sirotin).




## Tässä harjoituksessa käytämme GitHubia git:n kanssa.
Luodaan siis käyttäjä GitHubiin.
Itselläni on jo käyttäjä luotu GitHubiin koulun tunnuksilla, joten voin skipata tämän kohdan.

Luotuasi käyttäjän, oikealla on valikko "Your repositories" luodaan tänne uusi repository.

![Luo uusi repository](https://jernvall.com/wp-content/uploads/2018/05/CreateNewRepo.png)

![Luo uusi repository](https://jernvall.com/wp-content/uploads/2018/05/CreateRepository.png)

Loin repositoryn nimeltä "kalinka".
Sekä valitsin että readme.md luodaan automaattisesti ja linsenssiksi valitsin GNU GPL v3


#### Nyt meillä on tämä repository luotuna ja voimme aloittaa tekemällä siihen muutoksia git:n avulla.
![Repository luotu](https://jernvall.com/wp-content/uploads/2018/05/repoLuotu.png)


### Asennetaan git meidän xubuntu koneelle.</h3>
<pre class="prettyprint">sudo apt-get update
sudo apt-get install git</pre>
Tein itselleni kansiot github/omat kotikansioon.

Kopioidaan tänne juuri luotu repository, githubista näkee linkin tuosta "clone or download" kohdasta, mikä on merkitty vihreällä.

<pre class="prettyprint">git clone https://github.com/JamiJ/kalinka.git</pre>

Seuravaaksi git kysyy sinun käyttäjätunnusta ja salasanaa.
Annettuasi käyttäjätunnuksen ja salasanan git ohjelma cloonaa tämän repositoryn ja olet valmis muokkaamaan näitä tiedostoja, sekä lisäämään uusia.



Koska, meidän täytyy julkaista tämä B) kohta markdownilla, ruvetaan kirjoittamaan muokkauksia siis README.md tiedostoon.
Linkki minun githubin repositoryyn, jota muokkaamme. - [https://github.com/JamiJ/kalinka](https://github.com/JamiJ/kalinka)

#### Kaikki muokkaukset mitä teemme git:n kanssa, niistä tulee versiohistoria automaattisesti. Muunnan tämän wordpress postauksen markdowniksi ja jatkan kirjottamista GitHubiin, sekä tähän postaukseen.

### Muokataan tätä README.md tiedostoa niin näemme mitä tapahtuu

Git toimii siis siten, että kun tämä repository on kloonattu omalle koneelle, muokkaamme tiedostoa ihan perus "nano" komennolla ja sen jälkeen annamme komennot
<pre class="prettyprint">git add .
Tämä komento hakee tiedostot joita on muutettu ja lisää ne listalle mitä lähetetään eteenpäin git:llä

git commit
Tämä komento ajaa nämä tiedostot, mitä git add komennolla on muokattu uudeksi versioksi

git pull &amp;&amp; git push
Nämä komennot hakee git repositorystä uudet muokatut tiedostot, jos niitä on muokannut joku toinen henkilö ja puskee nämä meidän muutokset git repositoryyn</pre>


GitHub näyttää myös nämä kaikki korjaukset, mitä on tehty jokaiseen tiedostoon todella hyvin. Jokainen rivi mitä on muokattu, tai jos joitain tiedostoja on lisätty.

![Commits](https://jernvall.com/wp-content/uploads/2018/05/commits.png)

Tuolla näkyy tällähetkellä 5 committia, olen siis muuttanut tästä repositorystä tiedostoja viisi kertaa.
![Commits inside](https://jernvall.com/wp-content/uploads/2018/05/commits-inside.png)

Avataan vaikka tuo "Fixed git repo image file" ja katsotaan mitä muutoksia olen tehnyt.

![FixedRepo](https://jernvall.com/wp-content/uploads/2018/05/fixed-repo.png)

Olen muokannut kuvista rajaukset pois, sekä alimmasta kuvasta vanhan html markdownin pois ja vaihtanut sen githubin markdowniin.

Sitten vain jatketaan näiden samojen komentojen ajamista ja muokataan tarvittaessa.

## Tehtävä C) Aja oma salt tila git-varastosta
