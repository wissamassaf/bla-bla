[Cognitive Services](https://azure.microsoft.com/en-us/services/cognitive-services/) are a set of rest Apis that Enable natural and contextual interaction with tools that augment users' experiences using the power of machine-based intelligence.

## Purpose of the scriptr.io connector for NOAA
The purpose of this connector is to simplify and streamline the way you access Cognitive Services' APIs from scriptr.io, by providing you with a few native objects that you can directly integrate into your own scripts.


## Components
- microsoft/cognitive/emotion/config : a configuration file that contains key that the developer purchase from [cognitive-services](https://www.microsoft.com/cognitive-services/en-US/subscriptions)

- microsoft/cognitive/emotion/emotion : this object have a method that will Recognize the emotions expressed by one or more people in an image, as well as return a bounding box for the face. The emotions detected are happiness, sadness, surprise, anger, fear, contempt, and disgust or neutral.(emotionRecognition())

- microsoft/cognitive/textAnalytics/config : a configuration file that contains key that the developer purchase from [cognitive-services](https://www.microsoft.com/cognitive-services/en-US/subscriptions)

- microsoft/cognitive/textAnalytics/TextAnalyticsManager : this object have a method that will find out what users think of your brand—or any topic—by analyzing any English-language text to score the overall sentiment of it(sentiment()), a method that will automatically extract key phrases from English-language text to quickly identify the main points (keyPhrases()), and a method that will determine what language a piece of text is written in—from 120 supported languages.


## How to use
- Use the Import Modules feature to deploy the aforementioned scripts in your scriptr account, in a folder named "modules/microsoft".
- Create a developer account and an application at [Cognitive Services](https://www.microsoft.com/cognitive-services/en-US/subscriptions)
- Once done, make sure to specify the keys in the "config" files under emotion and textAnalytics ("subscriptionKey") .
- Create a test script in scriptr, or use one of the scripts provided in (microsoft/cognitive/textAnalytics/test) or (microsoft/cognitive/emotion/test).
emotion example: 
```
var config = require("./config");
var emotionManager = require("./emotion");
var em = new emotionManager.Emotion(config);
var params = {
	url:"http://media.gettyimages.com/videos/close-up-sad-face-of-homeless-black-man-looking-at-camera-talking-video-id348-15?s=640x640"
}
return em.emotionRecognition(params);
```
textAnalytics example:
```
var config = require("./config");
var TextAnalyticsManager = require("./TextAnalyticsManager");
var tam = new TextAnalyticsManager.TextAnalyticsManager(config);
var params = {
  "documents":[
    {"id":"string",
     "language":"en",
     "text":"amazing review thanks a lot."
    },
    {
     "id":"string1",
     "language":"en",
     "text":"worst reply ever"
    }
  ]
}
return tam.sentiment(params);
var detectParams = {
  "documents": [
    {
      "id": "string1",
      "text": "welcome"
    },
    {
      "id":"string2",
      "text":"bonjour"
    },
    {
      "id":"string3",
      "text":"te amo"
    }
  ]
}
return tam.detectLanguages(detectParams);

var params = {
  "documents":[
    {"id":"string",
     "language":"en",
     "text":"amazing review thanks a lot."
    },
    {
     "id":"string1",
     "language":"en",
     "text":"happy new year"
    }
  ]
}
return tam.keyPhrases(params);
```

