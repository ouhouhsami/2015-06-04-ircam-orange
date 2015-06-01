# Web Audio & Applications

Ircam, 4 juin 2015 - 12h15

Samuel Goldszmidt & Norbert Schnell

## Ircam → Web Audio

Samuel G. : Développeur Web
Norbert S. : Designer son et interaction

Les acquis initiaux

* Utilisation des technologies HTML5 sur les systèmes d'information et de gestion de l'Ircam (<audio> <video>) au CRI
* Utilisation de technologies Web Audio au sein de l'équipe APM Pôle ingénierie multimédia
* ISSM : objets connectés d'intéraction musicale

2 projets de recherche :

* WAVE (Web Audio Visualization/Edition)
* CoSiMa (Collaborative Situated Media, coordonné par Norbert Schnell)

Pourquoi un intérêt pour les technologies Web Audio

* Emergentes
* Accessibles

Web
3 millions de personnes utilisent un navigateur :
"Logiciel par défaut" et même Browser as an OS (exemple de Google Doc)
Comment "transférer" les savoir, les technologies, les algorithmes de l'Ircam sur la plateform Web et
1. Avoir de nouveaux champs de recherches ou en étendre, d'expérimentation et de retours utilisateurs
2. Rendre disponibles au plus grand nombre nos technologies
3. TTM hyper réduit

Importance du W3C

Pas d'installation lorsque navigateur est installé et qu'il respecte les standards, donc aller auprès des standards : ce qu'on a fait avec Web Audio API et WAC, et ce qu'on doit continuer à faire et utiliser les standards : si une killer app utilise un standard => compétition entre browser vendor => Ok. Exemple de Web RTC


Organisateur de la première Web Audio Conference

## Les technologies, Web Audio

~ 1995: <bgsound> <applet>
~ 1997: Flash
~ 2008: <audio>
~ 2010: Web Audio API, WebRTC (getUserMedia), WebSocket

### Web Audio API


* High-level JavaScript API for processing and synthesizing audio in web applications
* The paradigm: audio routing graph which connects AudioNodes to define an audio rendering.
* Underlying implementation in C / C++ code, but direct JavaScript processing and synthesis is supported

<audio> HTML5 element allows for basic streaming and audio playback, in recent browsers no more need to Flash and QuickTime.
But not enough for games and interactive applications, like DAW (Digital Audio Workstations), audio plugin effects and synthesizers ...
... and all we can imagine in a multimedia multi-user connected environment for music!

* Sample accurate scheduled sound playback
* Integration with <audio> and <video> media elements, getUserMedia(), WebRTC
* Spatialized audio
* Convolution engine
* Filters, Waveshaping, Oscillator
* AudioParameters
* Time-domain and frequency analysis (for visualization only at this time)


https://webaudiodemos.appspot.com/Vocoder/index.html

http://webaudiodemos.appspot.com/midi-synth/index.html


les projets développés actuellement

WAC was the first international conference dedicated to web audio technologies and applications.
The conference gathered web R&D developers, audio processing scientists, application designers and people involved in web standards.
The conference addressed research, development, design and standards concerned with emerging audio-related web technologies such as Web Audio API, Web RTC, WebSockets and JavaScript.


    Web Audio Papers
    Web Audio Talks
    Web Audio Demo/Poster
    Web Audio Gigs
    Plenary session of the W3C Audio Working Group



    How to port or reuse existing code with the Web Audio API: Flash, CSound, PNaCl, Emscripten
    "Usual audio computer fields" in native JavaScript: eg. Music Information Retrieval - Meyda library
    Tools for developers: eg. Web Audio tool in Firefox
    Audio UI: waves.ui, P5.js, Repovizz
    Audio Engine/Framework: waves.audio, Tones.JS
    Sound Synthesis, processing (binaural)
    Applications: MT5 (DAW), Tanguy (Synth), Telemeta, Noteflight, Hyperaudio, Lissajous ...


# Les performances obtenues,

Web Audio API vs. Native: Closing the Gap

    Native code is good at performance and flexibility
    Web Audio API code is good at distribution (browserify), security (web platform is sandboxed) and is "Ease of use" (web audio api is easy).
    Keynote by Paul Adenot WAC'2015

Possible "easy" improvments for audio performances in web audio context:

    With AudioWorker: no more thread boundaries to cross as Audio and JavaScript are on the same thread
    Use asm.js as it doesn't produce temporary objects to be garbage collected.
    Use SIMD.js. SIMD (Single Instruction Multiple Data) allows to perform operations on multiple data elements together which is particularly interesting in terms of performance in the case of audio buffer data processing.

For the bad news (denormals, lock-free/wait-free, context-switch) watch the video.

## Et autres technologies et standards Web Audio

### W3C Standards et implémentations

Audio Working Group
    * Web Audio API (Edge, Firefox, Chrome, Safari, Opera, iOS, Android Chrome)
    * Web Midi API (Chrome, Opera)

* WebSocket API (Tous navigateurs)

Web Real-Time Communications Working Group (+Device APIs Working Group)
    * WebRTC 1.0: Real-time Communication Between Browsers (Firefox, Chrome, Android Browser, Chrome for Android)
    * Media Capture and Streams (getUserMedia) (Edge, Firefox, Chrome, Opera, Android browser, Chrome for android)
    * MediaStream Recording
    * Audio output devices API
    * ...

Media capture task force

* Geolocation Working Group
    * Geolocation API Specification (puis Geolocation API Level 2) (Tous navigateurs)
    * DeviceOrientation Event Specification (Device Orientation et Device Motion API) (Tous navigateurs sauf Safari browser)


### Libraries et frameworks

#### waves.js, a library to easily build audio applications (WAVE project)


* UI: display temporal representations
* Audio: audio engine and scheduler
* LFO: audio processing


UI

 Presentation: WAC waves.ui (Chrome only)
Documentation: wavesjs.github.io

    Waveform - Display
    Markers - Display and Edit
    Segments - Display and Edit
    Break Point Functions (aka BPF) - Display and Edit
    Cursor
    Zoom/Move

Exemples d’applications

Some examples use cases: Blocs Gigognes Philippe Leroux, Opus 27 Anton Webern, Luna Park Georges Aperghis, Bachotheque J.-S Bach


audio components

    Core: Time Engine, Audio Time Engine
    Engines, extend Audio Time Engine, in charge of playing sound: Granular Engine, Metronome, Player-engine, Segment-Engine
    Masters, in charge of controling the playback and scheduling of engines:
        Play Control "start, pause, stop" - extends Time Engine to provide playback control of a Time Engine instance
        Scheduler (Simple-Scheduler)
        Transport (Provides synchronized scheduling of Time Engine instances)

Exemples d’applications

LFO

 LFO is a library that proposes an efficient API to formalize the processing and analysis of arbitrary data streams (eg. audio, video, sensor data).
By normalising the stream format in it's input and output, it allows to:

    analyse and manipulate the data through a uniform processing chain
    encapsulate common processing algorithms with a unified interface that can be shared and reused


a framework Collective-Soundworks for innovative audio and multimedia collaborative use cases. (CoSiMa project)

Exemples d’applications


# les perspectives à venir

Les options de tranferts de technologies
* Réinventer la roue
* Utiliser des méthodes
La meilleur solution se trouve entre les deux.

ES6 (ES 2015), ES7

Open source vs. Open data


