[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/hyperium/hyper/master/LICENSE)

#Ivy-YouTube
<p align="center">
  <img src="https://github.com/squiter/ivy-youtube/blob/master/demo.gif">
</p>

Ivy-YouTube is a simple plugin to query YouTube via emacs and play videos in your browser. 

**IMPORTANT:** Remeber to set your 'ivy-youtube-key' variable!

## Based on Helm-Youtube

This package was based on [Maximilian Roquemore](https://github.com/maximus12793)'s package called [helm-youtube](https://github.com/maximus12793/helm-youtube).  
Thanks Maximilian to create this awesome package.


## Installation 
1. M-x package-install: ivy-youtube

2. Obtain new google API key 
    [here](https://console.developers.google.com/ "Google Developer Console")

    ![Screenshot](https://github.com/squiter/ivy-youtube/blob/master/api.png)

3. **IMPORTANT:** Set 'ivy-youtube-key' variable


    ``` el
    M-x customize-variable ;; search 'ivy-youtube-key'
    Ivy Youtube Key: replace "NONE" with "API KEY" ;; FROM STEP 2
    ```

4. Set browse-url-generic and add to .emacs

 
    ``` el
    ;;start ivy-youtube.el
    (autoload 'ivy-youtube "ivy-youtube" nil t)
    (global-set-key (kbd "C-c y") 'ivy-youtube) ;; bind hotkey

    ;;set default browser for you will use to play videos/default generic
    (setq browse-url-browser-function 'browse-url-generic)
    (setq browse-url-generic-program "google-chrome-open-url")
    ```
5. Enjoy :) 
