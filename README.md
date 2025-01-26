# Using Google Fonts in the Canvas

A basic example of using a Google font on an HTML canvas. 

1. First we need to locate the static URL of the Google Font you want to use on the canvas. For the Google Lato font, the static URL is:

    ```
    https://fonts.gstatic.com/s/lato/v14/S6uyw4BMUTPHjx4wXiWtFCc.woff2
    ```
    
    As far as I can tell, these URLs are not documented, but they can be found by looking up the desired font using the Google FONT API endpoints:
    
    ```
    https://fonts.googleapis.com/css?family=Lato:400
    ```
    
    And then copying the static font URL out of the CSS:
  
    ```css
    /* latin */
    @font-face {
      font-family: 'Lato';
      font-style: normal;
      font-weight: 400;
      src: url(https://fonts.gstatic.com/s/lato/v23/S6uyw4BMUTPHjx4wXiWtFCc.woff2) format('woff2');
      unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
    }
    ```

2. Using JavaScript, we need to load the font using the static file reference:
  
    ```javascript
    let latoFont = new FontFace(
      "Lato",
      "url(https://fonts.gstatic.com/s/lato/v23/S6uyw4BMUTPHjx4wXiWtFCc.woff2)"
    );
    ```

3. After the font has loaded, we can use the font with the canvas using the ```font``` property and ```fillText``` method:
  
    ```javascript
    googleFont.load().then((font) => {
    
      document.fonts.add(font);
    
      context.fillStyle = "#fff";
      context.font = "60px Lato";
      context.fillText("Hello World!", 50, 100);
    
    });
    ```

***

## Repo Resources

* [W3C Markup Validator](https://validator.w3.org/)
* [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)

<br>
<a href="https://codeadam.ca">
<img src="https://cdn.codeadam.ca/images@1.0.0/codeadam-logo-coloured-horizontal.png" width="200">
</a>
