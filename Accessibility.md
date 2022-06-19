### Introduction
During the minor I got the privilege to listen to Leonie Watson talk about web accessibility. Leonie Watson herself is blind and works as an accessibility engineer. She had a really interesting presentation about her own experiences on the web and how 'far' we've come with accessibility for blind and visionally impaired people. I put 'far' in between quotes because I dont really think major improvements are made yet.

Leonie demonstrated how in these times people can choose between a vary of different voices to use for their screenreaders; different genders, accents and even if you'd want an adult or childlike voice. These voices are an improvement on the previous options. They were made to feel more human and less robotic, so people wouldn't mind to listen to these voices.

I found the whole presentation really interesting and this is the reason I wanted to write an article about Web Accesibility and how we, as front end developers and designers, can build better products when we implement web accessibility. Also the course _Human Centered Design_ really got me thinking about how people with disabilites navigate through the internet. 

### What is Web Accessibility?
MDN web docs defines accessibility as _Accessibility (often abbreviated to A11y — as in, "a", then 11 characters, and then "y") in web development means enabling as many people as possible to use websites, even when those people's abilities are limited in some way._
It's the practice of making your websites and apps usable by as many people as possible, despite their disabilities, devices or network speed. In some countries it's even mandatory by law to make accessible websites and apps. When they won't, they will be fined.

Building accessible sites benefits everyone.
* Semantic HTML, which improves accessibility but also improve SEO, making your website more findable.
* When your website or app is accessible, it demonstrates good ethics and morals, which improves your public image and gives good word-of-mouth advertisement.

When you want to make your website more accessible, you'll have to look beyond your own devices and how you use the web and start learning about how other people experience it. There are many different ways to use a computer when you have a disablility. I will list some of the main types of disabilities you'll need to know so you can design a better experience for them.


### Different types of disabilities and how to design for them
#### People with visual impairments
People with visual impairments include people with blindness, low level vision and color blindness. Many of these people use screen magnifiers or screen readers. For people with impaired vision it's very important that your website can be used with the keys like `TAB`. This key allows users to move from one element to another. 
Other who use screen readers, it's very important to use good semantic HTML. This is one practice that really lacks in the real world. Developers nowadays like to use a lot of different `div` elements. The problem is when they are using a lot of `div`, there is no hiërarchie and this makes it very difficult to navigate with a screen reader.

#### People with hearing impairments
Maybe when thinking of accessibilty, deaf and hard-of-hearing people are not the first to come to mind. I know I didn't. I thought their experience must be almost identical to mine, because at least they could see the website. But in a world where more content is moving to audio and video, I learned that a lot of content is lacking in the caption department. Most of the time there aren't even any and when there are captions, it's almost never good. They lack context and emotion. 
It should be a mandatory practice to at least offer captions for audio and video. 

#### People with mobility impairments
People with mobility impairments have disablites concerning movement, which might invlolve purely physical issues or neurological/genetic disorders that lead to weakness or loss of control in limbs. Some people might have difficulties using a mouse, while others might be more severly affected.
Also in these cases, it's important that your website is usable by using the keyboard.

#### People with cognitive impairments
Cognitie impairments refers to a broad range of disabilities. The range includes people with mental illnesses to people with learning disabilites, such as dyslexia. 
A good foundation for accessibilty for these people are:
* Delivering content in more than one way. ( Text-to-speech or video)
* Content that's easy to understand, such as text written using plain language standards.
* Good visual hiërarchie to make sure the focus is on important content.
* Minimizing distractions
* Consistency in your layout and navigation
* Good use of most known design patterns
* Clear error messages
* Easy to complete forms.

### People with older devices or slower internet
Unfortunatly not everyone will have the newest iPhone or Macbook. That's wht it's also important to make sure people with older devices or slower internet, can have a similar experience as people with the newest devices. 
During this minor I learned that as a Front end Developer it's important to forshadow most of the problems that will come with older devices. A lot of older browsers won't have the same features as the newer ones. Some won't even support JavaScript. This is where Progressive Enhancement comes in handy. It's the principle to start with HTML and CSS. Make sure everything works and later you can put the icing on the cake with JavaScript. It also implies you'll need to have fallback for certain features;

```css
/* need to check for support */
@supports selector(fieldset:focus) {
    input:focus, textarea:focus, select:focus, input[type='radio']:focus + label{
    border: 5px dotted  rgb(215, 153, 250);

    }
}

```

```js
if (hasFormValidation()) {
    // need to check for support for checkValidility
    errorMsg.insertAdjacentHTML('afterbegin', markup)


    submit.addEventListener('click', function (e) {
        isValid()
        addInvalidBorder()
    })


    form.addEventListener('keyup', () => {
        removeErrorMsg()
        removeInvalidBorder()
    })
}
else {
    checkInputs();
}
```

## Conclusion
During this minor I've met a lot of people within the field and unfortunatly a lot of them said that accessibility is one of the most overlooked subjects when making an application, which really surprised me because a lot of them did the same study and we almost always need to make sure our app works for everyone. It just shows the privilege of us people without disabilities.   
Even though I categorized what you should do for good accessibility, these principles should always be kept in mind when designing and making a website. When I will step into the work field, I will try my best to make sure everything I will work on, will be accessible for everyone. 


## Sources
[](https://monsido.com/web-accessibility)
[](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility)
[](https://developer.mozilla.org/en-US/docs/Web/Accessibility)