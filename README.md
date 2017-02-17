[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/hyperium/hyper/master/LICENSE)

#Ivy-YouTube
<p align="center">
  <img src="https://github.com/squiter/ivy-youtube/blob/master/demo1.png">
  <img src="https://github.com/squiter/ivy-youtube/blob/master/demo2.png">
  <img src="https://github.com/squiter/ivy-youtube/blob/master/demo3.png">
  <img src="https://github.com/squiter/ivy-youtube/blob/master/demo4.png">
</p>

Ivy-YouTube is a simple plugin to query YouTube via emacs and play videos in your browser.

**IMPORTANT:** Remeber to set your 'ivy-youtube-key' variable!

## Based on Helm-Youtube

This package was based on [Maximilian Roquemore](https://github.com/maximus12793)'s package called [helm-youtube](https://github.com/maximus12793/helm-youtube).
Thanks Maximilian to create this awesome package.


## Installation

The installation process is very simple:

- M-x package-install: ivy-youtube
- Obtain new google API key
    [here](https://console.developers.google.com/ "Google Developer Console")

    ![Screenshot](https://github.com/squiter/ivy-youtube/blob/master/api.png)

- **IMPORTANT:** Set 'ivy-youtube-key' variable

    ``` el
    M-x customize-variable ;; search 'ivy-youtube-key'
    Ivy Youtube Key: replace "NONE" with "API KEY" ;; FROM STEP 2
    ```

## Where do you want to play the video?

By default Ivy Youtube play the selected video in your default browser, but you can configure that:

### Change the default brownser:

Set browse-url-generic and add to .emacs

``` elisp
;;start ivy-youtube.el
(autoload 'ivy-youtube "ivy-youtube" nil t)
(global-set-key (kbd "C-c y") 'ivy-youtube) ;; bind hotkey

;;set default browser for you will use to play videos/default generic
(setq browse-url-browser-function 'browse-url-generic)
(setq browse-url-generic-program "google-chrome-open-url")
```

### Using an external player (beta)

You can set a external player to watch your videos, like `mpv` or
`vlc`. To do that you need to set the custom varialble
`ivy-youtube-play-at`: `M-x
customize-variable<RET>ivy-youtube-play-at<RET>`.
You can set in this field any binary that receives the youtube url as
parameter like: `/usr/bin/mpv` or `/usr/bin/vlc`.
