# 🐈📦 go-nyaa

[![Go Reference](https://pkg.go.dev/badge/github.com/irevenko/go-nyaa.svg)](https://pkg.go.dev/github.com/irevenko/go-nyaa)

> nyaa.si client library for Go

<p align="center"><img src="https://avatars.githubusercontent.com/u/28658394?s=200&v=4"></p>

<p align="center">Built on top of <a href="https://github.com/mmcdole/gofeed">gofeed</a>
<p align="center">Original idea <a href="https://github.com/ejnshtein/nyaa-api">ejnshtein/nyaa-api</a></p>


# Installation 🔨
```go get github.com/mmcdole/gofeed``` <br>
```go get github.com/irevenko/go-nyaa```

# Contributing 🤝
Contributions, issues and feature requests are welcome! 👍 <br>
Feel free to check [open issues](https://github.com/irevenko/go-nyaa/issues).

# Docs 📋
<a href="https://pkg.go.dev/github.com/irevenko/go-nyaa">Go reference</a>

## Search Example

```go
import ( 
    "fmt"
    "log"

	"github.com/irevenko/go-nyaa/nyaa"
)

func main() {
    opt := nyaa.SearchOptions{
        Query:    "LN",
        Category: "literature",
        SortBy:   "seeders",
        Filter:   "trusted-only",
    }

    torrents, err := nyaa.Search(opt)
    if err != nil {
        log.Fatal(err)
    }

    fmt.Println(torrents)
}
```

## SearchOptions
```go
type SearchOptions struct {
	Query    string
	Category string
	SortBy   string
	Filter   string
}
```
## Query
- your desired search string

## Category
* ```all``` - All Categories
* ```anime``` - All Anime
    * ```anime-amv``` 
    * ```anime-eng```
    * ```anime-non-eng```
    * ```anime-raw```
* ```audio``` - All Audio
    * ```audio-lossless``` 
    * ```audio-lossy```
* ```literature``` - All Literature
    * ```literature-eng``` 
    * ```literature-non-eng```
    * ```literature-raw``` 
* ```live-action``` - All Live Action
    * ```live-action-idol-prom``` 
    * ```live-action-eng```
    * ```live-action-non-eng```
    * ```live-action-raw```
* ```pictures``` - All Pictures
    * ```pictures-graphics``` 
    * ```pictures-photos``` 
* ```software``` - All Software
    * ```software-apps``` 
    * ```software-games```

## SortBy
- ```comments```
- ```downloads``` 
- ```date``` 
- ```seeders``` 
- ```leechers```
- ```size``` 

## Filter
- ```no-filter```
- ```no-remakes``` 
- ```trusted-only``` 


# Notes
- Pagination does not work with RSS
- Ascending sort does not work with RSS

# ToDo
- [x] Sort by comments, size, date, seeders, leechers, downloads
- [x] Filter: No filter, No remakes, Trusted only 
- [x] Search All
- [x] Search Anime
- [x] Search Literature
- [x] Search Audio
- [x] Search Live Action
- [x] Search Pictures
- [x] Search Software
- [ ] Add sukebei.nyaa.si support
- [ ] Scrap full description and comments from nyaa.si/view/...

# What I Learned 🧠
- RSS Feed, xml

# License 📑 
(c) 2021 Ilya Revenko. [MIT License](https://tldrlegal.com/license/mit-license)