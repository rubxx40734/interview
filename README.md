# interview
程式架構做到最大的沿用性、維護性，並於Readme說明你的想法 :

關於這部分的話，我認為「模組化」是相當重要的一環
在初學程式設計的時候，認為這部分好像還好，畫面或者功能有出來即可，但是隨著經驗累積，程式
越變越長，發現很難debug，很多東西都沒做好拆分，就很難除錯並且也不易於管理。
且如果做好拆分，就可以在很多專案中使用。像是如果把scss拆分成util,base全站設定,mediaquery等等，
這樣在別的地方就能使用自己常用的設定，可以節省很多時間。
關於維護性方面，我雖然還沒有團隊開發的經驗，但是我覺得程式撰寫的命名很重要，
可以讓團隊一目了然，知道這段函式在做甚麼，這個變數存取什麼樣的資料等等，然後再搭配ESLint，
這樣的話可以讓程式乾淨許多，閱讀起來也很直覺，不管維護開發都會節省許多時間

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
