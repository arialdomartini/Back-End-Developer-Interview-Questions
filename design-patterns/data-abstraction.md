# Data Abstraction

## [Krzysztof Grzybek](https://github.com/krzysztof-grzybek)

Data Abstraction violation:
```javascript
class Book {
    constructor(pages) {
        this.pages = pages;
    }
}

const myBook = new Book([{ text: 'content of the title page'}, { text: '...'}]);
const titlePage = myBook.pages[0];
```

Fixed:
```javascript
class Book {
    constructor(pages, title) {
        this.pages = pages;
        this.title = title;
    }

    getTitlePage() {
        return this.title || this.pages[0];
    }   
}

const myBook = new Book([{ text: 'content of the title page'}, { text: '...'}]);
const titlePage = myBook.getTitlePage();
```
