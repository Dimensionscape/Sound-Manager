# Sound Manager
 SoundManager provides a robust way to organize and control audio playback in OpenFL applications. Additionally, it includes features such as fade in and fade out volume control and more.

Usage: 
 ```haxe
var soundCollection:SoundCollection = new SoundCollection();
soundCollection.add(new SoundAsset("<unique-id>", "<asset-path>"));
SoundManager.init(soundCollection);

SoundManager.play("<unique-id>");
```

Populate sound collection by creating new SoundAsset objects or by casting dynamic, anonymous structures. Alternatively, you can create a new SoundCollection from an object or JSON structure:
```haxe
var soundCollection:SoundCollection = SoundCollection.fromJSON("<json-data>");

var soundCollection:SoundCollection = SoundCollection.fromObject(obj);

var soundCollection:SoundCollection = new SoundCollection();
soundCollection.add(cast {id:"<unique-id>",path:"<asset-path>"});
```

The Json Data looks like this:
```JSON
{
 "SoundCollection": [{
		"id": "<unique-id>",
		"path": "<asset-path>"
	}, {
		"id": "<unique-id>",
		"path": "<asset-path>"
	}, {
		"id": "<unique-id>",
		"path": "<asset-path>"
	}, {
		"id": "<unique-id>",
		"path": "<asset-path>"
	}]
}
```

Fade in and out Background Music(BGM):
```haxe
SoundManager.playBGM("<id>").fadeIn(<end-time-in-milliseconds>).fadeOut(<start-time-in-milliseconds>);
```
Create callbacks for onComplete and onStop:
```haxe
SoundManager.playBGM("<id>").onComplete(<function>).onStop(<function>);
```



