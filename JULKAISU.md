# kultapoika.fi – julkaisuohje

Tämä kansio (`kultapoika-site/`) on valmis julkaistavaksi sellaisenaan: `index.html` + `kuvat/`.
Sivu on staattinen, joten se ei tarvitse palvelinta, tietokantaa tai Shopifyta.

## 1. Julkaise Netlifyyn (n. 5 min, ilmainen)

1. Mene osoitteeseen **app.netlify.com** ja luo tunnus (sähköposti tai GitHub).
2. Valitse **Add new site → Deploy manually**.
3. Vedä koko `kultapoika-site`-kansio selaimeen (ei zipiä, kansio sellaisenaan).
4. Sivu on heti osoitteessa `jotain-satunnaista.netlify.app`. Tarkista, että se toimii.

Vaihtoehdot: Cloudflare Pages tai Vercel toimivat samalla tavalla. Jos haluat päivittää sivua
jatkossa suoraan Claudesta, GitHub-repo + Netlify on paras yhdistelmä – sanot vain "julkaise",
ja muutos menee live-sivulle.

## 2. Kytke kultapoika.fi

Netlifyssä: **Domain management → Add a domain → kultapoika.fi**. Netlify näyttää DNS-tietueet.

Domainin rekisteröijän hallintapaneelissa (esim. Louhi, Domainhotelli, Zoner, Hostingpalvelu):

| Tyyppi | Nimi | Arvo |
|---|---|---|
| A | @ | `75.2.60.5` |
| CNAME | www | `<sivusi>.netlify.app` |

Tai helpompi: siirrä nimipalvelimet Netlifyn nimipalvelimille (Netlify DNS), niin kaikki hoituu
automaattisesti. HTTPS-sertifikaatti tulee itsestään 5–30 minuutissa DNS:n päivityttyä.

## 3. Ennen kuin mainostat – tarkistuslista

- [ ] **Footer:** vaihda `[Yritys Oy, Y-tunnus]` oikeaksi (index.html, hae tekstiä `Yritys Oy`).
- [ ] **WhatsApp Business** -tili numerolle 040 178 8921: profiilikuvaksi `kultapoika-logo/kultapoika-profiilikuva-512.png`,
      tervehdysviesti brändisivun pohjasta, aukioloajat.
- [ ] **Tietosuojaseloste**: käsittelet nimiä, puhelinnumeroita ja henkilökorttikuvia → tarvitset selosteen
      (GDPR). Lyhyt sivu riittää; voin kirjoittaa pohjan. Linkki footeriin.
- [ ] **Hintatakuun ehdot** yhdellä lauseella UKK:hon: "kirjallinen tarjous samoista esineistä, enintään 7 pv vanha".
- [ ] **Video**: kun se on kuvattu, laita `kuvat/kultapoika-lahetys.mp4` ja avaa index.html:ssä kommentoitu `<video>`-tagi.
- [ ] **Posti**: vakuutetun lähetyksen hinnat ja vakuutusraja tarkistettu, oma sopimus tai Prepaid-koodit valmiina.
- [ ] **Mittaus**: Meta Pixel + Google Analytics -koodit `<head>`-osaan, jos aiot mainostaa. WhatsApp-napin
      klikkaus kannattaa merkitä konversioksi (kaikissa napeissa on `data-wa`-attribuutti, johon voi kiinnittää tapahtuman).
- [ ] **Google Business Profile** nimellä Kultapoika – ilmainen ja näkyy haussa "kullan osto".

## 4. Päivän hinta

Sivu hakee kullan hinnan automaattisesti latautuessa (gold-api.com + frankfurter.dev, molemmat ilmaisia,
ei avainta). Jos haku epäonnistuu, käytetään `CONFIG.spotEurPerGram`-arvoa index.html:n lopussa.
Päivitä sitä silloin tällöin varmuuden vuoksi. Ostoprosentti on `CONFIG.payoutRate` (0.85).

## 5. Tiedostot

- `index.html` – koko sivu (tyylit ja skripti sisällä)
- `kuvat/` – kaikki kuvat, favicon, jakokuva (`og.jpg`)
- Logot ja alkuperäiset kuvat: `../kultapoika-logo/` ja `../kultapoika-kuvat/`
- Brändiohje: https://claude.ai/code/artifact/ce71c922-c24c-4ad2-b54a-6377a1e08b1d
- Videokäsikirjoitus: `../kultapoika-video-kasikirjoitus.md`
