# Ion.Sound 2.0.0

> English description | <a href="readme.ru.md">Описание на русском</a>

JavaScript plugin for playing sounds on user actions and page events.
* <a href="http://ionden.com/a/plugins/ion.sound/en.html">Project page and demos</a>
* <a href="http://ionden.com/a/plugins/ion.sound/ion.sound-2.0.0.zip">Download ion.sound-2.0.0.zip</a>

***

## Description
Today websites are full of events (new mail, new chat-message, content update etc.). Often it is not enough to indicate this events only visually to get user attention. You need sounds! This library, made for playing small sounds, will help you with this task.
* Ion.Sound freely distributed under terms of <a href="http://ionden.com/a/plugins/licence-en.html" target="_blank">MIT licence</a>.
* 25 free sounds included


## Supported browsers
### Desktop Windows, OS X, Linux:

* Google Chrome
* Mozilla Firefox
* Microsoft Internet Explorer 9.0+
* Opera 12.16+
* Safari 5.1+ (Safari on Windows requires QuickTime to play sounds)

### Mobile:

* iOS Safari and others (with some <a href="https://developer.apple.com/library/safari/documentation/audiovideo/conceptual/using_html5_audio_video/device-specificconsiderations/device-specificconsiderations.html" target="_blank">restrictions</a>)
* Android Google Chrome and others (with some restrictions also)
* WP8 Internet Explorer

<a href="http://caniuse.com/audio" target="_blank">More about browser support</a>


## Dependencies
* No dependencies, jQuery dependency was dropped since 2.0


## Usage
Import this libraries:
* ion.sound.min.js

Prepare sound-files (25 sounds are included) and put them in some folder (eg. "sounds"):
* my_cool_sound.mp3
* my_cool_sound.ogg

It is not enough to have only Mp3-file, you should make Ogg-file too, because not all browsers support Mp3.<br/>
You can easily convert you Mp3-s to Ogg-s at <a href="http://media.io/" target="_blank">Media.io</a> or at <a href="https://cloudconvert.org/formats#audio" target="_blank">CloudConvert.org</a>.


## Initialisation
To initialise plugin call this method:
```javascript
ion.sound({
    sounds: [
        {
            name: "my_cool_sound"
        },
        {
            name: "notify_sound",
            volume: 0.2
        },
        {
            name: "alert_sound",
            volume: 0.3,
            preload: false
        }
    ],
    volume: 0.5,
    path: "sounds/",
    preload: true
});
```

And play sound!
```javascript
// Simple
ion.sound.play("my_cool_sound");
```


## Settings
<table class="options">
    <thead>
        <tr>
            <th>Settings</th>
            <th>Default</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>sounds</td>
            <td>-</td>
            <td>
                You should set your own sounds collection here. This is an array of objects. Sound object structure:<br/>
                <code>name: "sound_name"</code> name of the sound file, without extension, !required<br/>
                <code>volume: 0.2</code> override default volume<br/>
                <code>preload: true</code> override default preload setting
            </td>
        </tr>
        <tr>
            <td>path</td>
            <td>-</td>
            <td>Example: <code>"sounds/"</code>. Optional property, set path to folder with sounds, if not set will be the same with html file.</td>
        </tr>
        <tr>
            <td>preload</td>
            <td>false</td>
            <td>Optional property, if set to <code>true</code>, will try to preload that sound file on page load.</td>
        </tr>
        <tr>
            <td>volume</td>
            <td>0.5</td>
            <td>Optional property, will set base volume from 0.0 to 1.0</td>
        </tr>
    </tbody>
</table>

An example of a customised plugin:
```javascript
ion.sound({
    sounds: [
        {
            name: "message_alert",
            volume: 1.0
        },
    ],
    path: "sounds/",
    preload: true
});
```


## Methods

### ion.sound.play
```javascript
// Simple
ion.sound.play("my_cool_sound");

// Change volume and play
ion.sound.play("my_cool_sound", {
    volume: 0.9
});

// Loop sound playback
ion.sound.play("my_cool_sound", {
    loop: true
});

// Repeat sound for 3 times and reset volume
ion.sound.play("my_cool_sound", {
    volume: 0.2,
    loop: 3
});
```

### ion.sound.stop
```javascript
// stop sound by name
ion.sound.stop("my_cool_sound");

// stop all sounds
ion.sound.stop();
```

### ion.sound.destroy
```javascript
// destroy sound by name
ion.sound.destroy("my_cool_sound");

// destroy all sounds
ion.sound.destroy();
```


## Update history
* 2.0.0: June 31, 2014 - dropped jQuery dependency, new API, loop sounds feature
* 1.3.0: November 30, 2013 - new methods "stop" and "kill". Ability to reset sound volume
* October 13, 2013 - now you can set individual volume for any sound. Improved test environment
* September 21, 2013 - plugin moved to jQuery namespace, new method and 10 new sounds
* September 08, 2013 - iOS not playing sound bug fix
* September 08, 2013 - Little enhancement
* September 07, 2013 - Plugin release