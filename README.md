# Tal-unter-Wasser
based on Panellum
## About
based on HTML5, CSS3, JavaScript, and WebGL, 

## Browser Compatibility
Since it based on Pannellum it is built with web standards, it requires a modern browser to function.

#### Full support (with appropriate graphics drivers):
* Firefox 23+
* Chrome 24+
* Safari 8+
* Internet Explorer 11+
* Edge

The support list is based on feature support. As only recent browsers are tested, there may be regressions in older browsers.

#### Not officially supported:
Mobile / app frameworks are not officially supported. They may work, but they're not tested and are not the targeted platform.

## License for 360°- View
Pannellum is distributed under the MIT License. For more information, read the file `COPYING` or peruse the license [online](https://github.com/mpetroff/pannellum/blob/master/COPYING).

In the past, parts of Pannellum were based on [three.js](https://github.com/mrdoob/three.js) r40, which is licensed under the [MIT License](https://github.com/mrdoob/three.js/blob/44a8652c37e576d51a7edd97b0f99f00784c3db7/LICENSE).

The panoramic image provided with the examples is licensed under the [Creative Commons Attribution-ShareAlike 3.0 Unported License](http://creativecommons.org/licenses/by-sa/3.0/).

## Credits
copyright of all pictures are by twinC Gmbh

```HTML
<!DOCTYPE html>//Bleibt gleich

// https://code.visualstudio.com

// 1. Neue Seite erstellen
// 2. Hotspots erstellen
// 3. Css (Style) erstellen

<html>//Bleibt gleich

    <head>//Bleibt gleich

        <title>Panorama</title> // Bleibt gleich

        <meta charset="utf-8">// Bleibt gleich

        <meta name="viewport" content="width=device-width, initial-scale=1.0">// Bleibt gleich

        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/pannellum@2.5.6/build/pannellum.css"/>// Bleibt gleich

        <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/pannellum@2.5.6/build/pannellum.js"></script>// Bleibt gleich

        <script src="https://vjs.zencdn.net/7.1.0/video.js"></script>// Bleibt gleich

        <link href="https://vjs.zencdn.net/7.19.1/video-js.css" rel="stylesheet" />// Bleibt gleich

        <script src="https://pannellum.org/js/videojs-pannellum-plugin.js"></script>// Bleibt gleich

        <style> 
		</style> 
       </head> 
       
       <body>
		</body>

```
## Creating media-links in CSS // You have to upload your Data on a Server with unrestricted access. The CSS is integrated in the HTML.
example:
 	The CSS is triggered by the dot and the ID you put behind.
```CSS
            .menu {
                    height: 240px; 
                    width: 242px;
                    background: url("https://Beispiel.png"); // Link to the Data
                    background-size: contain
            }
```
## Creating new Hotspots HTML
```HTML
### Scenelink "hotSpots": 
	[ //Anfang aller Hotspots

                            // Für jeden neuen Hotspot werden 2 geschweifte Klammern gemacht:
                            // {
                            //              <---- Hier werden alle Parameter eingefügt             
                            // }
                            //

                    
                                {
                                    "pitch": 0, // (Oben / Unten) 0 = mittig
                                    "yaw": 90.0, // (Rechts / Links) 360 °= Gerade aus
                                    "type": "Scene", // Entweder Scene oder Info in die Gänsefüsschen | Scene wird verwendet falls der Hotspot zu einer anderen Scene(Seite) führen soll. | Info wird bei einem normalen Bild verwendet.
                                    "text": "Hauptmenü", // Titel für den Hotspot | Nichts spezifisches
                                    "sceneId": "Hauptmenue",// Wird nur im Falle von "type": "scene" verwendet (Beispiel oben) ansonsten kann diese Zeile gelöscht werden | Titel der Scene (Z.66)
                                    "cssClass": "Hauptmenue", // Name der Css-Klasse siehe| Muss genau gleich geschrieben werden (Großschreibung)
                                    "createTooltipFunc": hotspot, // type of Hotspot
                                    "createTooltipArgs": "Hauptmenü",  // Textdecription 
    
                                },
```
### Information or pictures "hotSpots": 
```HTML
	[ //Anfang aller Hotspots

                            // Für jeden neuen Hotspot werden 2 geschweifte Klammern gemacht:
                            // {
                            //              <---- Hier werden alle Parameter eingefügt             
                            // }
                            //

                                {
                                "pitch": 0, // (Oben / Unten) 0 = mittig
                                "yaw": 90.0, // (Rechts / Links) 360 °= Gerade aus
                                "type": "Info", // Entweder Scene oder Info in die Gänsefüschen | Scene wird verwendet falls der Hotspot zu einer anderen Scene(Seite) führen soll. | Info wird bei einem normalen Bild verwendet.
                                "text": "Steckbrief Roter Panda", // Titel für den Hotspot | Nichts spezifisches
                                "cssClass": "Steckbrief", // Name der Css-Klasse siehe (Stylesheet-ID) | Muss genau gleich geschrieben werden (Großschreibung)
                                "createTooltipFunc": hotspot, // type of Hotspot
                                "createTooltipArgs": "", // Textdecription 

                            },
```
## Creating new Scenes
```HTML
 "scenes": {
                    
                    // Hier werden alle Seiten eingefügt
    
                    "Beispiel": { //Titel der Scene
                            "title": "Beispiel", // Titel der Seite
                            "hfov": 110, // Bleibt gleich
                            "pitch": 0, // (Oben / Unten) 0 = mittig | Startausrichtung
                            "yaw": 360, // (Rechts / Links) 360 °= Gerade aus | Startausrichtung
                            "type": "equirectangular",// Bleibt gleich
                            "panorama": "https://Beispiel.png", //Panorama Bild
    
                            "hotSpots": [ //Anfang aller Hotspots in dieser Szene

                                {
                                    "pitch": 0, // (Oben / Unten) 0 = mittig
                                    "yaw": 90.0, // (Rechts / Links) 360 °= Gerade aus
                                    "type": "Scene", // Entweder Scene oder Info in die Gänsefüschen | Scene wird verwendet falls der Hotspot zu einer anderen Scene(Seite) führen soll. | Info wird bei einem normalen Bild verwendet.
                                    "text": "Weiter", // Titel für den Hotspot | Nichts spezifisches
                                    "sceneId": "",// Wird nur im Falle von "type": "scene" verwendet (Beispiel oben) ansonsten kann diese Zeile gelöscht werden | Titel der Scene
                                    "cssClass": "Roter Panda Gehege2", // Name der Css-Klasse siehe | Muss genau gleich geschrieben werden (Großschreibung)
                                    "createTooltipFunc": hotspot, //Bleibt gleich
                                    "createTooltipArgs": "Ab ins Gehege", //Bleibt gleich
    
                                }, // Komma immer bei einem weiteren Hotspot
                            ] // Ende aller Hotspots in der Szene
                    },
```
