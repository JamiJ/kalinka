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
sudo apt-get install git
sudo apt-get install salt-minion</pre>
Tein itselleni kansiot github/omat kotikansioon.

Kopioidaan tänne juuri luotu repository, githubista näkee linkin tuosta "clone or download" kohdasta, mikä on merkitty vihreällä.

<pre class="prettyprint">git clone https://github.com/JamiJ/kalinka.git</pre>
![Clone](https://jernvall.com/wp-content/uploads/2018/05/Git-1.png)




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
Tämän komennon jälkeen joudut antamaan oman käyttäjätunnuksen, sekä salasanan.

GitHub näyttää myös nämä kaikki korjaukset, mitä on tehty jokaiseen tiedostoon todella hyvin. Jokainen rivi mitä on muokattu, tai jos joitain tiedostoja on lisätty.

![Commits](https://jernvall.com/wp-content/uploads/2018/05/commits.png)

Tuolla näkyy tällähetkellä 5 committia, olen siis muuttanut tästä repositorystä tiedostoja viisi kertaa.
![Commits inside](https://jernvall.com/wp-content/uploads/2018/05/commits-inside.png)

Avataan vaikka tuo "Fixed git repo image file" ja katsotaan mitä muutoksia olen tehnyt.

![FixedRepo](https://jernvall.com/wp-content/uploads/2018/05/fixed-repo.png)

Olen muokannut kuvista rajaukset pois, sekä alimmasta kuvasta vanhan html markdownin pois ja vaihtanut sen githubin markdowniin.

Sitten vain jatketaan näiden samojen komentojen ajamista ja muokataan tarvittaessa.

## Tehtävä C) Aja oma salt tila git-varastosta
### Olen luonut jo aiemmin toisen repositoryn mitä käytän tässä tehtävässä hyväksi
![GitHub.com/JamiJ/saltexamplelocal](https://github.com/JamiJ/saltexamplelocal)

Tämä repository asentaa saltin avulla apachen, sekä konfiguroi asetustiedostoja siten, että käyttäjien omat kotisivut toimivat ja niissä toimii myös php. Sekä luo tyhjän .txt tiedoston tmp/ kansioon.
Jos haluat tarkemmin tietää miten salt toimii tai mitä tässä salt tilassa ajetaan. ![Jernvall.com-Viiko2-Palvelinten-Hallinta](https://jernvall.com/2018/04/05/viikko-2-palvelinten-hallinta/) täältä voit katsoa miten olen luonut nämä tiedostot ja mitä ne tekevät.
Tämän tehtävän tärkein tiedosto on "high.sh" mikä sisältää rivin
<pre class="prettyprint">salt-call --local state.highstate --file-root srv/salt/</pre>
Tässä siis ajetaan state.highstate lokaalisti, omalla koneella ja missä käytetään salt tiedostojen paikkana srv/salt kansiota, mikä kloonataan tästä repositorystä.

Voimme siis kloonata tämän tiedoston ajamalla komennon
<pre class="prettyprint">git clone https://github.com/JamiJ/saltexamplelocal.git</pre>
ja ajamalla tämän salt tilan komennolla. Muista että sinun pitää olla tämän "saltexamplelocal/" kansion sisällä, jotta tämä komento toimii
<pre class="prettyprint">sudo bash high.sh</pre>
Katsotaan mitä tämä kometo luo ja tekee.

![clone](https://jernvall.com/wp-content/uploads/2018/05/clone-1.png)

![Asenneus](https://jernvall.com/wp-content/uploads/2018/05/asennus-1.png)

Näemme, että apache2 asennetaan ja php laitetaan toimimaan käyttäjillä, sekä kotihakemiston sivut.

![Toimii](https://jernvall.com/wp-content/uploads/2018/04/2-1.png)