```
  handlePrev = () => {
    this.img.prev();
  }

  handleNext = () => {
    this.img.next();
  }
```

```
     <Carousel ref={dom => { this.img = dom; }}>
       .......
      </Carousel>
```

