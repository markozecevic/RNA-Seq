# RNA-Seq
## Materijali za deo kursa posvecen analizi RNA-Seq podataka

Linux okruzenje sa instaliranim neophodnim paketima i RStudiom je dokerizovano i okaceno na [Docker Hub](https://hub.docker.com/r/markoz/rnastudio/).

Nakon [instalacije Docker-a](https://docs.docker.com/install/), potrebno je odraditi pull (~4.3 GB download).
```console
docker pull markoz/rnastudio
```
Zatim treba klonirati GitHub repo sa meterijalima.
```console
git clone git@github.com:markozecevic/RNA-Seq.git
```
Kada u lokalu imate i Docker image i materijale, pokrenucete Docker kontejner komandom (potrebno je zameniti `/putanja/do/repozitorijuma/RNA-Seq` sa pravom putanjom kloniranog repozitorijuma):
```console
docker run -e PASSWORD=etf -p 8787:8787 -v /putanja/do/repozitorijuma/RNA-Seq:/home/rstudio/materijali -e ROOT=TRUE markoz/rnastudio
```


U browseru otvoriti http://localhost:8787/ (user: "rstudio, pass: "etf"). 

Sledece komande ce podesiti radni folder i izrenderovati materijale:

```r
setwd("~/materijali")
bookdown::render_book("index.Rmd", "bookdown::gitbook")
```