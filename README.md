# RNA-Seq
## Materijali za deo kursa posvecen analizi RNA-Seq podataka

Linux okruzenje sa instaliranim neophodnim paketima i RStudiom je dokerizovano i okaceno na [Docker Hub](https://hub.docker.com/r/markoz/rnastudio/).

Nakon [instalacije Docker-a](https://docs.docker.com/install/), potrebno je odraditi pull (~4.3 GB download).
```
docker pull markoz/rnastudio
```
Zatim treba klonirati GitHub repo sa meterijalima.
```
git clone git@github.com:markozecevic/RNA-Seq.git
```
Sada kada imate image i materijale, pokrenucete Docker kontejner komandom:
```
docker run -e PASSWORD=etf -p 8787:8787 -v /Users/markoz/work/etf/RNA-Seq:/home/rstudio/materijali -e ROOT=TRUE markoz/rnastudio
```


U browseru otvoriti http://localhost:8787/ (user: "rstudio, pass: "etf"). 

Sledece komande ce podesiti radni folder i izrenderovati materijale:

```r
setwd("~/materijali")
bookdown::render_book("index.Rmd", "bookdown::gitbook")
```