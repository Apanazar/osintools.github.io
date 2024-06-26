## Общие

> Справочник: https://osintframework.com

---

* https://github.com/Lissy93/web-check

__Об инструменте__:
> `Получите представление о внутренней работе данного веб-сайта: выявите потенциальные векторы атак, проанализируйте архитектуру сервера, просмотрите конфигурации безопасности и узнайте, какие технологии использует сайт.`

> `В настоящее время на панели мониторинга отображаются: информация об IP, цепочка SSL, записи DNS, файлы cookie, заголовки, информация о домене, правила обхода поиска, карта страниц, местоположение сервера, реестр перенаправлений, открытые порты, трассировка маршрута, расширения безопасности DNS, производительность сайта, трекеры, связанные имена хостов, футпринты.`

![webcheck](https://github.com/Apanazar/osintools.github.io/blob/main/img/webcheck.png)

__Запуск__: 
`docker run -p 3000:3000 lissy93/web-check` 
[`localhost:3000`](http://localhost:3000/)

---

* https://github.com/projectdiscovery/katana  
__Об инструменте__:
<details><summary>   katana --help</summary>

   Katana is a fast crawler focused on execution in automation
pipelines offering both headless and non-headless crawling.

Usage:
  ./katana [flags]

Flags:
INPUT:
   -u, -list string[]  target url / list to crawl
   -resume string      resume scan using resume.cfg

CONFIGURATION:
   -r, -resolvers string[]       list of custom resolver (file or comma separated)
   -d, -depth int                maximum depth to crawl (default 3)
   -jc, -js-crawl                enable endpoint parsing / crawling in javascript file
   -jsl, -jsluice                enable jsluice parsing in javascript file (memory intensive)
   -ct, -crawl-duration value    maximum duration to crawl the target for (s, m, h, d) (default s)
   -kf, -known-files string      enable crawling of known files (all,robotstxt,sitemapxml), a minimum depth of 3 is required to ensure all known files are properly crawled.
   -mrs, -max-response-size int  maximum response size to read (default 9223372036854775807)
   -timeout int                  time to wait for request in seconds (default 10)
   -aff, -automatic-form-fill    enable automatic form filling (experimental)
   -fx, -form-extraction         extract form, input, textarea & select elements in jsonl output
   -retry int                    number of times to retry the request (default 1)
   -proxy string                 http/socks5 proxy to use
   -H, -headers string[]         custom header/cookie to include in all http request in header:value format (file)
   -config string                path to the katana configuration file
   -fc, -form-config string      path to custom form configuration file
   -flc, -field-config string    path to custom field configuration file
   -s, -strategy string          Visit strategy (depth-first, breadth-first) (default "depth-first")
   -iqp, -ignore-query-params    Ignore crawling same path with different query-param values
   -tlsi, -tls-impersonate       enable experimental client hello (ja3) tls randomization
   -dr, -disable-redirects       disable following redirects (default false)

DEBUG:
   -health-check, -hc        run diagnostic check up
   -elog, -error-log string  file to write sent requests error log

HEADLESS:
   -hl, -headless                    enable headless hybrid crawling (experimental)
   -sc, -system-chrome               use local installed chrome browser instead of katana installed
   -sb, -show-browser                show the browser on the screen with headless mode
   -ho, -headless-options string[]   start headless chrome with additional options
   -nos, -no-sandbox                 start headless chrome in --no-sandbox mode
   -cdd, -chrome-data-dir string     path to store chrome browser data
   -scp, -system-chrome-path string  use specified chrome browser for headless crawling
   -noi, -no-incognito               start headless chrome without incognito mode
   -cwu, -chrome-ws-url string       use chrome browser instance launched elsewhere with the debugger listening at this URL
   -xhr, -xhr-extraction             extract xhr request url,method in jsonl output

SCOPE:
   -cs, -crawl-scope string[]       in scope url regex to be followed by crawler
   -cos, -crawl-out-scope string[]  out of scope url regex to be excluded by crawler
   -fs, -field-scope string         pre-defined scope field (dn,rdn,fqdn) or custom regex (e.g., '(company-staging.io|company.com)') (default "rdn")
   -ns, -no-scope                   disables host based default scope
   -do, -display-out-scope          display external endpoint from scoped crawling

FILTER:
   -mr, -match-regex string[]       regex or list of regex to match on output url (cli, file)
   -fr, -filter-regex string[]      regex or list of regex to filter on output url (cli, file)
   -f, -field string                field to display in output (url,path,fqdn,rdn,rurl,qurl,qpath,file,ufile,key,value,kv,dir,udir)
   -sf, -store-field string         field to store in per-host output (url,path,fqdn,rdn,rurl,qurl,qpath,file,ufile,key,value,kv,dir,udir)
   -em, -extension-match string[]   match output for given extension (eg, -em php,html,js)
   -ef, -extension-filter string[]  filter output for given extension (eg, -ef png,css)
   -mdc, -match-condition string    match response with dsl based condition
   -fdc, -filter-condition string   filter response with dsl based condition

RATE-LIMIT:
   -c, -concurrency int          number of concurrent fetchers to use (default 10)
   -p, -parallelism int          number of concurrent inputs to process (default 10)
   -rd, -delay int               request delay between each request in seconds
   -rl, -rate-limit int          maximum requests to send per second (default 150)
   -rlm, -rate-limit-minute int  maximum number of requests to send per minute

UPDATE:
   -up, -update                 update katana to latest version
   -duc, -disable-update-check  disable automatic katana update check

OUTPUT:
   -o, -output string                file to write output to
   -sr, -store-response              store http requests/responses
   -srd, -store-response-dir string  store http requests/responses to custom directory
   -or, -omit-raw                    omit raw requests/responses from jsonl output
   -ob, -omit-body                   omit response body from jsonl output
   -j, -jsonl                        write output in jsonl format
   -nc, -no-color                    disable output content coloring (ANSI escape codes)
   -silent                           display output only
   -v, -verbose                      display verbose output
   -debug                            display debug output
   -version                          display project version

</details>

__Запуск__:
* Go Package - `go install github.com/projectdiscovery/katana/cmd/katana@latest`
* Docker:
`docker pull projectdiscovery/katana:latest`
`docker run projectdiscovery/katana:latest -u https://tesla.com -system-chrome -headless`

---
* app.netlas.io  
__Об инструменте__:
> `Whois, IP/Domain info, DNS Search, Domain Whois Search, Certificates Search`
>_Attention :_ `Лимит 30 реквестов `

![netatlas](https://github.com/Apanazar/osintools.github.io/blob/main/img/netlas.png)

---


* ip2geolocation.com  
__Об инструменте__:
![ip2geo](https://github.com/Apanazar/osintools.github.io/blob/main/img/ip2geo.png)

---

* https://github.com/TheYahya/enola  
__Об инструменте__:
> `Это сестра Sherlock, современный блестящий инструмент CLI, написанный совместно с Golang, который поможет вам: 🔎 Искать аккаунты в социальных сетях по имени пользователя в социальных сетях`

![enola](https://github.com/Apanazar/osintools.github.io/blob/main/img/enola.png)
__Запуск__:
>`enola {username}`
* Go Package - `go install github.com/theyahya/enola/cmd/enola@latest`
* Docker:
`NONE`

---

* https://dnsdumpster.com  
__Об инструменте__:
> Поиск поддоменов и DNS серверов

![dnsdump](https://github.com/Apanazar/osintools.github.io/blob/main/img/dnsdump.png)

---

* https://www.shodan.io
  > В представлении не нуждается

---

* https://github.com/dwisiswant0/go-dork  
__Об инструменте__:
> `Поисковик по дорк запросам`

![godork](https://github.com/Apanazar/osintools.github.io/blob/main/img/godork.png)

__Запуск__:
> `go-dork -q "inurl:'...'"`
* Go Package - `GO111MODULE=on go install github.com/dwisiswant0/go-dork@latest`
* Docker:
`NONE`

---

* http://similarsites.com  
__Об инструменте__:
> `Поиск схожих сайтов`

![similar](https://github.com/Apanazar/osintools.github.io/blob/main/img/similar.png)

---

* https://github.com/megadose/OnionSearch  
__Об инструменте__:
> `Единый поиск по нескольким поисковым системам:`
> `ahmia, darksearchio, onionland, notevil, darksearchenginer, phobos, onionsearchserver, torgle, onionsearchengine, tordex, tor66, tormax, haystack, multivac, evosearch, deeplink`

<details><summary>onionsearch --help</summary>
usage: onionsearch [-h] [--proxy PROXY] [--output OUTPUT]
                  [--continuous_write CONTINUOUS_WRITE] [--limit LIMIT]
                  [--engines [ENGINES [ENGINES ...]]]
                  [--exclude [EXCLUDE [EXCLUDE ...]]]
                  [--fields [FIELDS [FIELDS ...]]]
                  [--field_delimiter FIELD_DELIMITER] [--mp_units MP_UNITS]
                  search

positional arguments:
  search                The search string or phrase

optional arguments:
  -h, --help            show this help message and exit
  --proxy PROXY         Set Tor proxy (default: 127.0.0.1:9050)
  --output OUTPUT       Output File (default: output_$SEARCH_$DATE.txt), where $SEARCH is replaced by the first chars of the search string and $DATE is replaced by the datetime
  --continuous_write CONTINUOUS_WRITE
                        Write progressively to output file (default: False)
  --limit LIMIT         Set a max number of pages per engine to load
  --engines [ENGINES [ENGINES ...]]
                        Engines to request (default: full list)
  --exclude [EXCLUDE [EXCLUDE ...]]
                        Engines to exclude (default: none)
  --fields [FIELDS [FIELDS ...]]
                        Fields to output to csv file (default: engine name link), available fields are shown below
  --field_delimiter FIELD_DELIMITER
                        Delimiter for the CSV fields
  --mp_units MP_UNITS   Number of processing units (default: core number minus 1)
</details>

__Запуск__:
> `onionsearch "computer" --engines tor66 deeplink phobos --limit 3`
* PyPI - `pip3 install onionsearch`
* Docker:
`NONE`

---

* https://github.com/s-rah/onionscan  
__Об инструменте__:
> `.onion сетевой сканер`

![onionscan](https://github.com/Apanazar/osintools.github.io/blob/main/img/onionscan.png)

__Запуск__:
* Go Package:
>Compile - `go install github.com/s-rah/onionscan`
>Run without compiling - `go run github.com/s-rah/onionscan.go`
* Docker: ``
`NONE`

---

## Instagramm

* https://github.com/novitae/sterraxcyl  
__Об инструменте:__
> `Уникальный инструмент SOCMINT для получения информации об аккаунте instagram от его подписчиков`

![insta](https://github.com/Apanazar/osintools.github.io/blob/main/img/insta.png)  
__Запуск:__
> `sterra export -u USERNAME`
* PyPI - `pip3 install sterra`
* Docker:
`NONE`

---

* https://github.com/Datalux/Osintgram  
__Об инструменте:__
> `Osintgram - это инструмент OSINT для Instagram. Он предлагает интерактивную оболочку для проведения анализа аккаунта Instagram любого пользователя по его нику`

<details>
<summary> --help</summary>

- addrs           Get all registered addressed by target photos
- captions        Get user's photos captions
- comments        Get total comments of target's posts
- followers       Get target followers
- followings      Get users followed by target
- fwersemail      Get email of target followers
- fwingsemail     Get email of users followed by target
- fwersnumber     Get phone number of target followers
- fwingsnumber    Get phone number of users followed by target
- hashtags        Get hashtags used by target
- info            Get target info
- likes           Get total likes of target's posts
- mediatype       Get user's posts type (photo or video)
- photodes        Get description of target's photos
- photos          Download user's photos in output folder
- propic          Download user's profile picture
- stories         Download user's stories  
- tagged          Get list of users tagged by target
- wcommented      Get a list of user who commented target's photos
- wtagged         Get a list of user who tagged target
</details>

![osintgram](https://github.com/Apanazar/osintools.github.io/blob/main/img/osintgram.png)

__Запуск:__
* Docker Compose - `docker-compose run osintgram <target>`

---

## Twitter

## VK

## Discord

## Скам/Фиш БД
