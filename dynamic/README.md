# Anki Dynamic Configurable Template #

This is Anki dynamic configurable note template(facebook color style) with below fetures:

1. option checkbox to load and save configuration
2. js helper function to autoplay OTF(on the fly media) online audio 
3. js helper function to hide/display hint section
4. js helper function to help customize content and highlight tag 
5. version detection and update.

## Template Usage ##

- You can click checkbox on head section to change options. This change will be effective during one review session(iOS/Desktop version only)

![](https://raw.githubusercontent.com/ninja33/anki-templates/master/dynamic/images/sample_006.jpg)

- You can change these options on note template's style section by true/false setting. That will be effective on all card's lifecycle.
```
    //audio autoplay
    config.audio    = false; 

    //hide or display hint section
    config.fold     = true;  
    
    //other config might be added
    config.example  = false;  
```
- You can click notes/sentences section head(blue) to hide and display section content.

![](https://raw.githubusercontent.com/ninja33/anki-templates/master/dynamic/images/sample_007.jpg)

## Template Preview ##
- Status with hidden notes/sentences section on/off, audio autoplay on/off and example of definition on/off.
![](https://raw.githubusercontent.com/ninja33/anki-templates/master/dynamic/images/sample_003.jpg)
![](https://raw.githubusercontent.com/ninja33/anki-templates/master/dynamic/images/sample_004.jpg)

- Display hint section and show version update information at head section
![](https://raw.githubusercontent.com/ninja33/anki-templates/master/dynamic/images/sample_002.jpg)

This Template was inspired by [ecator](https://github.com/ecator/anki-theme-basic-baidu-jp-en)
