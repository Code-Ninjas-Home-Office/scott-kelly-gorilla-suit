# Scott Kelly ISS Gorilla Mini-Game Tutorial

```package
arcade-timers=github:microsoft/arcade-timers
sk_images=github:bmarslandCN/sk_images
```

```template
namespace SpriteKind {
    export const Crew = SpriteKind.create()
}
scene.onOverlapTile(SpriteKind.Player, assets.tile`myTile1`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`myTile2`)
    timer.after(500, function () {
        tiles.setTileAt(location, assets.tile`myTile1`)
    })
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`dvdsTile`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`topBlankTile`)
    game.showLongText("During our personal time, we watched movies on DVD! We can request movies to be sent with our other supplies.", DialogLayout.Center)
    game.showLongText("You have collected " + objectsCollected + " of 6 objects!", DialogLayout.Center)
    objectsCollected += 1
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`computerTile`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`topBlankTile`)
    game.showLongText("Astronauts can keep in touch with their families with video calls and emails. I also update my social media from space!", DialogLayout.Center)
    game.showLongText("You have collected " + objectsCollected + " of 6 objects!", DialogLayout.Center)
    objectsCollected += 1
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`closedBoxTile`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`openBoxTile`)
    gorillaGame()
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`damagedPanelRight`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`solarPanelRight`)
    info.changeScoreBy(1)
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`spaceWalkBottom`, function (sprite, location) {
    if (sprite.image.equals(sk_images.spacesuitRight) || sprite.image.equals(sk_images.spacesuitLeft)) {
        sprite.setImage(sk_images.scottKellyLeft)
        tiles.setWallAt(tiles.getTileLocation(24, 11), true)
        tiles.setWallAt(tiles.getTileLocation(24, 12), true)
    }
})
controller.left.onEvent(ControllerButtonEvent.Pressed, function () {
    if (scottKellySprite.image.equals(sk_images.scottKellyRight)) {
        scottKellySprite.setImage(sk_images.scottKellyLeft)
    }
    if (scottKellySprite.image.equals(sk_images.gorillasuitRight)) {
        scottKellySprite.setImage(sk_images.gorillasuitLeft)
    }
    if (scottKellySprite.image.equals(sk_images.spacesuitRight)) {
        scottKellySprite.setImage(sk_images.spacesuitLeft)
    }
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`bookTile`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`topBlankTile`)
    game.showLongText("We get a little free time each day, which was great to pursue hobbies like reading.", DialogLayout.Center)
    game.showLongText("You have collected " + objectsCollected + " of 6 objects!", DialogLayout.Center)
    objectsCollected += 1
})
function spaceWalkGame () {
    game.showLongText("Let's go for a space walk! Try to fix all the broken solar panels!", DialogLayout.Center)
    info.setScore(0)
    scottKellySprite.setImage(sk_images.spacesuitRight)
    for (let index = 0; index < 3; index++) {
        tiles.setTileAt(tiles.getTileLocation(randint(8, 14), randint(15, 16)), assets.tile`damagedPanelLeft`)
        tiles.setTileAt(tiles.getTileLocation(randint(8, 14), randint(18, 19)), assets.tile`damagedPanelLeft`)
        tiles.setTileAt(tiles.getTileLocation(randint(17, 23), randint(15, 16)), assets.tile`damagedPanelRight`)
        tiles.setTileAt(tiles.getTileLocation(randint(17, 23), randint(18, 19)), assets.tile`damagedPanelRight`)
    }
}
scene.onOverlapTile(SpriteKind.Player, assets.tile`myTile21`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`myTile20`)
    timer.after(500, function () {
        tiles.setTileAt(location, assets.tile`myTile21`)
    })
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`myTile16`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`myTile18`)
    timer.after(1000, function () {
        tiles.setTileAt(location, assets.tile`myTile16`)
    })
})
controller.right.onEvent(ControllerButtonEvent.Pressed, function () {
    if (scottKellySprite.image.equals(sk_images.scottKellyLeft)) {
        scottKellySprite.setImage(sk_images.scottKellyRight)
    }
    if (scottKellySprite.image.equals(sk_images.gorillasuitLeft)) {
        scottKellySprite.setImage(sk_images.gorillasuitRight)
    }
    if (scottKellySprite.image.equals(sk_images.spacesuitLeft)) {
        scottKellySprite.setImage(sk_images.spacesuitRight)
    }
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`myTile17`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`myTile19`)
    timer.after(1000, function () {
        tiles.setTileAt(location, assets.tile`myTile17`)
    })
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`damagedPanelLeft`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`solarPanelLeft`)
    info.changeScoreBy(1)
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`spaceWalkTile`, function (sprite, location) {
    tiles.setTileAt(tiles.getTileLocation(25, 11), assets.tile`transparency16`)
    tiles.setTileAt(tiles.getTileLocation(25, 12), assets.tile`transparency16`)
    spaceWalkGame()
})
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
}
scene.onOverlapTile(SpriteKind.Player, assets.tile`myTile10`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`bottomBlankTile`)
    game.showLongText("Did you know the entire ISS is run on 1.5 million lines of code?!", DialogLayout.Center)
    game.showLongText("You have collected " + objectsCollected + " of 6 objects!", DialogLayout.Center)
    objectsCollected += 1
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`beakerTile`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`bottomBlankTile`)
    game.showLongText("Astronauts spend a LOT of our time working on experiments in space. I worked on a moldy plant experiment!", DialogLayout.Center)
    game.showLongText("You have collected " + objectsCollected + " of 6 objects!", DialogLayout.Center)
    objectsCollected += 1
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`clipboardTile`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`bottomBlankTile`)
    game.showLongText("We have lots of tasks and chores to complete every day - even on the weekends! ", DialogLayout.Center)
    game.showLongText("You have collected " + objectsCollected + " of 6 objects!", DialogLayout.Center)
    objectsCollected += 1
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`spaceWalkTop`, function (sprite, location) {
    if (sprite.image.equals(sk_images.spacesuitRight) || sprite.image.equals(sk_images.spacesuitLeft)) {
        sprite.setImage(sk_images.scottKellyLeft)
        tiles.setWallAt(tiles.getTileLocation(24, 11), true)
        tiles.setWallAt(tiles.getTileLocation(24, 12), true)
    }
})
let crew: Sprite = null
let scottKellySprite: Sprite = null
let objectsCollected = 0
scene.setBackgroundImage(sk_images.scottKellySplash)
game.showLongText("Hello! I'm astronaut Scott Kelly!", DialogLayout.Bottom)
game.showLongText("Come spend a day aboard the International Space Station with me!", DialogLayout.Bottom)
game.showLongText("Navigate the ISS to find some things I interacted with daily to learn more about life in the space station!", DialogLayout.Bottom)
game.setDialogCursor(sk_images.jumpsuit)
scene.setBackgroundImage(sk_images.spaceBackground)
tiles.setCurrentTilemap(tilemap`internationalSpaceStation`)
objectsCollected = 1
scottKellySprite = sprites.create(sk_images.scottKellyRight, SpriteKind.Player)
scottKellySprite.z = 10
tiles.placeOnTile(scottKellySprite, tiles.getTileLocation(3, 2))
controller.moveSprite(scottKellySprite)
scene.cameraFollowSprite(scottKellySprite)
for (let index = 0; index < 6; index++) {
    crew = sprites.create(sk_images.crewMember, SpriteKind.Crew)
    tiles.placeOnRandomTile(crew, assets.tile`bottomBlankTile`)
    tiles.setTileAt(crew.tilemapLocation(), assets.tile`bottomBlankTileCrew`)
    if (Math.percentChance(50)) {
        animation.runImageAnimation(
        crew,
        assets.animation`crewAnimRight`,
        randint(250, 750),
        true
        )
    } else {
        animation.runImageAnimation(
        crew,
        assets.animation`crewAnimLeft`,
        randint(250, 750),
        true
        )
    }
}
forever(function () {
    if (objectsCollected == 7) {
        let scareCount = 0
        tiles.setCurrentTilemap(tilemap`blankTilemap`)
        sprites.destroy(scottKellySprite)
        for (let value of sprites.allOfKind(SpriteKind.Crew)) {
            sprites.destroy(value)
        }
        scene.setBackgroundImage(sk_images.scottKellySplash)
        game.showLongText("Thanks for spending a day with me on the International Space Station! I hope you learned a lot and had some fun, too!", DialogLayout.Bottom)
        if (info.score() == 1) {
            game.showLongText("Thanks for fixing that solar panel!", DialogLayout.Bottom)
        } else if (info.score() > 1) {
            game.showLongText("Thanks for fixing those " + info.score() + " solar panels!", DialogLayout.Bottom)
        }
        if (scareCount == 1) {
            game.showLongText("And, great job scaring 1 crewmate in that gorilla suit!", DialogLayout.Bottom)
        } else if (scareCount > 1) {
            game.showLongText("And, great job scaring " + scareCount + " crewmates in that gorilla suit!", DialogLayout.Bottom)
        }
        game.gameOver(true)
    }
})
```

```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "images.g.jres": "{\n    \"cnKJDtVJQzG5,*N(\": {\n        \"namespace\": \"(iA\",\n        \"id\": \"cnKJDtVJQzG5,*N(\",\n        \"mimeType\": \"application/mkcd-animation\",\n        \"data\": \"ZjQwMTEwMDAxMDAwMDQwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwZWVlZTAwMjIwMjAwMDBlMDQ0NDQwZDIyMDIwMDAwNGY0NDQ0ZDQzMDAzMDBmNWRmNDQ0NGQ0MjAyMjIwZjFkZmY0ZjQ0NDIwMjIyMjIxZWY0NDQ0NDQwMDIyMjI0MWUyZjQ0ZmQ0MjAyMjIyMjUyMjRlNDQwNDIzMjIwMDAwMjIyMjAyMDIzMjAyMDAwMDIwMjIzMjIyMDIwMDAwMDAwMDIwMzIyMjAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDBlZWVlMDAyMjAyMDAwMGUwNDQ0NDBkMjIwMjAwMDA0ZjQ0NDRkNDMwMDMwMGY1ZGY0NDQ0ZDQyMDIyMjBmMWRmZjRmNDQ0MjAyMjIyMjFlZjQ0NDQ0NDAwMjIyMjQxZTJmNDRmZDQyMDIyMjIyNTIyNGU0NDA0MjMyMjAwMDAyMjIyMDIwMjMyMDIwMDAwMjAyMjMyMjIwMjAwMDAwMDAwMjAzMjIyMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMGVlZWUwMDIyMDIwMDAwZTA0NDQ0MGQyMjAyMDAwMDRmNDQ0NGQ0MzAwMzAwZjVkZjQ0NDRkNDIwMjIyMGYxZGZmNGY0NDQyMDIyMjIyMWVmNDQ0NDQ0MDAyMjIyNDFlMmY0NGZkNDIwMjIyMjI1MjI0ZTQ0MDQyMzIyMDAwMDIyMjIwMjAyMzIwMjAwMDAyMDIyMzIyMjAyMDAwMDAwMDAyMDMyMjIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMGVlZWUwMDIyMDIwMDAwZTA0NDQ0MGQyMjAyMDAwMDRmNDQ0NGQ0MzAwMzAwZjVkZjQ0NDRkNDIwMjIyMGYxZGZmNGY0NDQyMDIyMjIyMWVmNDQ0NDQ0MDAyMjIyNDFlMmY0NGZkNDIwMjIyMjI1MjI0ZTQ0MDQyMzIyMDAwMDIyMjIwMjAyMzIwMjAwMDAyMDIyMzIyMjAyMDAwMDAwMDAyMDMyMjIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDA=\",\n        \"displayName\": \"crewAnimRight\"\n    },\n    \"anim1\": {\n        \"namespace\": \"myAnimations\",\n        \"id\": \"anim1\",\n        \"mimeType\": \"application/mkcd-animation\",\n        \"data\": \"ZjQwMTEwMDAxMDAwMDQwMDAwMDAwMDAwMDAwMDAwMDAwMGVlZWUwMDAwMDAwMDAwZDA0NDQ0MGUwMDAwMjAyMjRkNDQ0NGY0MDAwMDIwMjI0ZDQ0NDRmZDVmMDAzMDAzNDQ0ZjRmZmQxZjAyMjIwMjQ0NDQ0NGZlMTIyMjIyMDI0ZGY0NGYyZTE0MjIyMjAwNDA0NGU0MjI1MjIyMjIwMjIwMjAyMjIyMDAwMDIyMzIyMjIzMjIwMjAwMDAyMDIzMjIyMzAyMDAwMDAwMDAyMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwZWVlZTAwMDAwMDAwMDBkMDQ0NDQwZTAwMDAyMDIyNGQ0NDQ0ZjQwMDAwMjAyMjRkNDQ0NGZkNWYwMDMwMDM0NDRmNGZmZDFmMDIyMjAyNDQ0NDQ0ZmUxMjIyMjIwMjRkZjQ0ZjJlMTQyMjIyMDA0MDQ0ZTQyMjUyMjIyMjAyMjAyMDIyMjIwMDAwMjIzMjIyMjMyMjAyMDAwMDIwMjMyMjIzMDIwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDBlZWVlMDAwMDAwMDAwMGQwNDQ0NDBlMDAwMDIwMjI0ZDQ0NDRmNDAwMDAyMDIyNGQ0NDQ0ZmQ1ZjAwMzAwMzQ0NGY0ZmZkMWYwMjIyMDI0NDQ0NDRmZTEyMjIyMjAyNGRmNDRmMmUxNDIyMjIwMDQwNDRlNDIyNTIyMjIyMDIyMDIwMjIyMjAwMDAyMjMyMjIyMzIyMDIwMDAwMjAyMzIyMjMwMjAwMDAwMDAwMjAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDBlZWVlMDAwMDAwMDAwMGQwNDQ0NDBlMDAwMDIwMjI0ZDQ0NDRmNDAwMDAyMDIyNGQ0NDQ0ZmQ1ZjAwMzAwMzQ0NGY0ZmZkMWYwMjIyMDI0NDQ0NDRmZTEyMjIyMjAyNGRmNDRmMmUxNDIyMjIwMDQwNDRlNDIyNTIyMjIyMDIyMDIwMjIyMjAwMDAyMjMyMjIyMzIyMDIwMDAwMjAyMzIyMjMwMjAwMDAwMDAwMjAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDA=\",\n        \"displayName\": \"crewAnimLeft\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myImages\"\n    }\n}",
  "images.g.ts": "// Auto-generated code. Do not edit.\nnamespace myImages {\n\n    helpers._registerFactory(\"image\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"animation\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"crewAnimRight\":\n            case \"cnKJDtVJQzG5,*N(\":return [img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . e e e e . . \n2 2 2 . . . . . . e 4 4 4 4 d . \n2 2 2 . . . . . f 4 4 4 4 4 4 d \n. 3 3 . . . 5 f f d 4 4 4 4 4 d \n. 2 2 2 . 2 1 f f d 4 f 4 f 4 4 \n. 2 2 2 2 2 1 2 f e 4 4 4 4 4 4 \n. . 2 2 2 2 1 4 2 e 4 f f 4 4 d \n. 2 2 2 2 2 5 2 2 2 e 4 4 4 4 . \n3 2 2 2 . . . . 2 2 2 2 2 . 2 . \n2 3 2 . . . . . . 2 2 2 2 3 2 2 \n2 . . . . . . . . . . 2 2 3 2 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . e e e e . . \n2 2 2 . . . . . . e 4 4 4 4 d . \n2 2 2 . . . . . f 4 4 4 4 4 4 d \n. 3 3 . . . 5 f f d 4 4 4 4 4 d \n. 2 2 2 . 2 1 f f d 4 f 4 f 4 4 \n. 2 2 2 2 2 1 2 f e 4 4 4 4 4 4 \n. . 2 2 2 2 1 4 2 e 4 f f 4 4 d \n. 2 2 2 2 2 5 2 2 2 e 4 4 4 4 . \n3 2 2 2 . . . . 2 2 2 2 2 . 2 . \n2 3 2 . . . . . . 2 2 2 2 3 2 2 \n2 . . . . . . . . . . 2 2 3 2 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . e e e e . . \n2 2 2 . . . . . . e 4 4 4 4 d . \n2 2 2 . . . . . f 4 4 4 4 4 4 d \n. 3 3 . . . 5 f f d 4 4 4 4 4 d \n. 2 2 2 . 2 1 f f d 4 f 4 f 4 4 \n. 2 2 2 2 2 1 2 f e 4 4 4 4 4 4 \n. . 2 2 2 2 1 4 2 e 4 f f 4 4 d \n. 2 2 2 2 2 5 2 2 2 e 4 4 4 4 . \n3 2 2 2 . . . . 2 2 2 2 2 . 2 . \n2 3 2 . . . . . . 2 2 2 2 3 2 2 \n2 . . . . . . . . . . 2 2 3 2 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . e e e e . . \n2 2 2 . . . . . . e 4 4 4 4 d . \n2 2 2 . . . . . f 4 4 4 4 4 4 d \n. 3 3 . . . 5 f f d 4 4 4 4 4 d \n. 2 2 2 . 2 1 f f d 4 f 4 f 4 4 \n. 2 2 2 2 2 1 2 f e 4 4 4 4 4 4 \n. . 2 2 2 2 1 4 2 e 4 f f 4 4 d \n. 2 2 2 2 2 5 2 2 2 e 4 4 4 4 . \n3 2 2 2 . . . . 2 2 2 2 2 . 2 . \n2 3 2 . . . . . . 2 2 2 2 3 2 2 \n2 . . . . . . . . . . 2 2 3 2 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`];\n            case \"crewAnimLeft\":\n            case \"anim1\":return [img`\n. . . . . . . . . . . . . . . . \n. . e e e e . . . . . . . . . . \n. d 4 4 4 4 e . . . . . . 2 2 2 \nd 4 4 4 4 4 4 f . . . . . 2 2 2 \nd 4 4 4 4 4 d f f 5 . . . 3 3 . \n4 4 f 4 f 4 d f f 1 2 . 2 2 2 . \n4 4 4 4 4 4 e f 2 1 2 2 2 2 2 . \nd 4 4 f f 4 e 2 4 1 2 2 2 2 . . \n. 4 4 4 4 e 2 2 2 5 2 2 2 2 2 . \n. 2 . 2 2 2 2 2 . . . . 2 2 2 3 \n2 2 3 2 2 2 2 . . . . . . 2 3 2 \n2 2 3 2 2 . . . . . . . . . . 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . e e e e . . . . . . . . . . \n. d 4 4 4 4 e . . . . . . 2 2 2 \nd 4 4 4 4 4 4 f . . . . . 2 2 2 \nd 4 4 4 4 4 d f f 5 . . . 3 3 . \n4 4 f 4 f 4 d f f 1 2 . 2 2 2 . \n4 4 4 4 4 4 e f 2 1 2 2 2 2 2 . \nd 4 4 f f 4 e 2 4 1 2 2 2 2 . . \n. 4 4 4 4 e 2 2 2 5 2 2 2 2 2 . \n. 2 . 2 2 2 2 2 . . . . 2 2 2 3 \n2 2 3 2 2 2 2 . . . . . . 2 3 2 \n2 2 3 2 2 . . . . . . . . . . 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . e e e e . . . . . . . . . . \n. d 4 4 4 4 e . . . . . . 2 2 2 \nd 4 4 4 4 4 4 f . . . . . 2 2 2 \nd 4 4 4 4 4 d f f 5 . . . 3 3 . \n4 4 f 4 f 4 d f f 1 2 . 2 2 2 . \n4 4 4 4 4 4 e f 2 1 2 2 2 2 2 . \nd 4 4 f f 4 e 2 4 1 2 2 2 2 . . \n. 4 4 4 4 e 2 2 2 5 2 2 2 2 2 . \n. 2 . 2 2 2 2 2 . . . . 2 2 2 3 \n2 2 3 2 2 2 2 . . . . . . 2 3 2 \n2 2 3 2 2 . . . . . . . . . . 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . e e e e . . . . . . . . . . \n. d 4 4 4 4 e . . . . . . 2 2 2 \nd 4 4 4 4 4 4 f . . . . . 2 2 2 \nd 4 4 4 4 4 d f f 5 . . . 3 3 . \n4 4 f 4 f 4 d f f 1 2 . 2 2 2 . \n4 4 4 4 4 4 e f 2 1 2 2 2 2 2 . \nd 4 4 f f 4 e 2 4 1 2 2 2 2 . . \n. 4 4 4 4 e 2 2 2 5 2 2 2 2 2 . \n. 2 . 2 2 2 2 2 . . . . 2 2 2 3 \n2 2 3 2 2 2 2 . . . . . . 2 3 2 \n2 2 3 2 2 . . . . . . . . . . 2 \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`];\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"song\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><variables><variable id=\"#]7@18%z*XJCeJ_PqkUy\">mySprite</variable></variables><block type=\"pxt-on-start\" x=\"0\" y=\"0\"><statement name=\"HANDLER\"><block type=\"run_image_animation\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#]7@18%z*XJCeJ_PqkUy\">mySprite</field></block></value><value name=\"frames\"><block type=\"animation_editor\"><field name=\"frames\">assets.animation`crewAnimRight`</field><data>{\"commentRefs\":[],\"fieldData\":{\"frames\":\"(iA.cnKJDtVJQzG5,*N(\"}}</data></block></value><value name=\"frameInterval\"><shadow type=\"timePicker\"><field name=\"ms\">500</field></shadow></value><value name=\"loop\"><shadow type=\"toggleOnOff\"><field name=\"on\">false</field></shadow></value><next><block type=\"run_image_animation\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#]7@18%z*XJCeJ_PqkUy\">mySprite</field></block></value><value name=\"frames\"><block type=\"animation_editor\"><field name=\"frames\">assets.animation`crewAnimLeft`</field><data>{\"commentRefs\":[],\"fieldData\":{\"frames\":\"myAnimations.anim1\"}}</data></block></value><value name=\"frameInterval\"><shadow type=\"timePicker\"><field name=\"ms\">500</field></shadow></value><value name=\"loop\"><shadow type=\"toggleOnOff\"><field name=\"on\">false</field></shadow></value></block></next></block></statement></block></xml>",
  "main.ts": "let mySprite: Sprite = null\nanimation.runImageAnimation(\nmySprite,\nassets.animation`crewAnimRight`,\n500,\nfalse\n)\nanimation.runImageAnimation(\nmySprite,\nassets.animation`crewAnimLeft`,\n500,\nfalse\n)\n",
  "pxt.json": "{\n    \"name\": \"Scott Kelly ISS Project Image File\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"Timers\": \"github:microsoft/arcade-timers#v1.1.0\",\n        \"sk_images\": \"github:bmarslandCN/sk_images#df2d124bd3b89ef07d2b59c27ec767545b01e08f\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"images.g.jres\",\n        \"images.g.ts\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.12.55\",\n        \"tag\": \"v1.12.55\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/0b8917880a46a30b0f35218153e52853fa47e114\",\n        \"target\": \"1.12.55\",\n        \"pxt\": \"8.5.66\"\n    },\n    \"preferredEditor\": \"tsprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile1\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3cvb3b27vNzdu9vd293dzd3L293b273N3bvb3du93M3dy9vd273czd27293b273N3cvb3dvd3c3du9vdvbu83N3L293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile\"\n    },\n    \"tile2\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273d27u9zdvbzd3Zu73N29u93du7nc3b283d27u9zdvbvd3bu73N29vN3d3d3d3b273d3d3d3dvbzd3bu73N29u93dW7nc3b283d2bu9zdvbvd3bu13N29vN3du7vc3b273d3d3d3dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile0\"\n    },\n    \"tile3\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3du9vd3b273d293d3dbWjd3bvb3d1taN3dvdvd3W1o3d273d3dbWjd3b3b291taN3d29273W1o3d2727vbbWjd3dvdu91paN3du9vb3Wlo3d3b293daWjd3bvb3d1taN3dvd3d3W1o3d27293dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile1\"\n    },\n    \"tile4\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3du9vd3b273d1mZmbdbWjdbWZmZtbdi91mZmZmZt1rbWZmZmZmZmttZmZmZmZma21mZmZmZmZrbYaWmYZmZmttZpaZZmZma22GlpmGZmZr3WZmZmZm3WvdbWZmZtbdi93dZmZm3W1o3d27293dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile2\"\n    },\n    \"tile5\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAALu7u7u7u7u7u7u7u7u7u7uGaIZohmiGaIZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGZoZmhmaGaIZohmiGaLu7u7u7u7u7u7u7u7u7u7sAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile3\"\n    },\n    \"tile6\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9vdy8zM29u7290MAADc28vb3QwAANzbu9vdDAAA3NvL290MAADc27vb3QwAANzby9vdDAAA3N27290MAADc3cvb3QwAANzdu9vdDAAA3N3L290MAADc27vb3cvMzNvby9vd3d3d3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile4\"\n    },\n    \"tile7\": {\n        \"data\": \"hwQQABAAAACwa2ZmZma2C7uLZmZmZrgLu4uIiIiIuAuGiGZmZma2C4ZmaGZmZrYLhmaGZmZmtguGZmZoZma2C4ZmZoZmZrYLhmZmZmhmtguGZmZmhma4C4ZmZmZmaLgLhmZmZmaGuAuGaGZmZma4C7u7u7u7u7sLu7u7u7u7uwAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile5\"\n    },\n    \"tile8\": {\n        \"data\": \"hwQQABAAAACwa2ZmZma2C7CLZmZmZrgLsIuIiIiIuAuwa2ZmZma2C7BrZmZmZrYLsItmZmZmuAuwi4iIiIi4C7BrZmZmZrYLsGtmZmZmtguwi2ZmZma4C7CLiIiIiLgLsGtmZmZmtguwa2ZmZma2C7CLZmZmZrgLsIuIiIiIuAuwa2ZmZma2Cw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile6\"\n    },\n    \"tile9\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAALu7u7u7u7sAu7u7u7u7uwuGaGZmhoi4C2ZoZmZmhrYLZmhmZmZotgtmaGZmhma2C2ZoZmZoZrYLZmhmhmZmtgtmaGZoZma2C2ZohmZmZrYLZmhoZmZmtguGiGZmZma2C7uLZmZmZrgLu4uIiIiIuAuwa2ZmZma2Cw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile7\"\n    },\n    \"tile10\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAC7u7u7u7u7sLu7u7u7u7uwi2ZmZmaGaLCLaGZmZmZosIuGZmZmZmiwi2ZoZmZmaLBrZoZmZmZosGtmZmhmZmiwa2ZmhmZmaLBrZmZmaGZosGtmZmaGZmiwa2ZmZmaIaLCLiIiIiLi7sItmZmZmuLuwa2ZmZma2Cw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile8\"\n    },\n    \"tile11\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9vdy8zM2927290MAADc3cvb3QwAANzdu9vdDAAA3N3L290MAADc3bvb3QwAANzdy9vdy8zM2927293d3d3d3cvb3b27u93du9vdvbm53d3L2929m7vd3bvb3b21td3dy9vdvbu73d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile9\"\n    },\n    \"tile14\": {\n        \"data\": \"hwQQABAAAAAAALC7AAAAsAAAu8ubmZnLALDLu7u7u7sAu7vb3d3d3bDLu93d3d3du7vb3d3d3d3Lu93d3d3d3bvb3d3d3d3dy9vdvbvd3d272929u93d3cvb3b273d3du9vd3d3d3d3L293d3b273bvb3d3dvbvdy9vd3d29u927293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile12\"\n    },\n    \"tile15\": {\n        \"data\": \"hwQQABAAAAALAAAAuwsAALyZmbm8uwAAu7u7u7u8CwDd3d3dvbu7AN3d3d3du7wL3d3d3d29u7vd3d3d3d27vN27293d3b273b3du9vdvbzdvd272929u9293bvb3b283b3dvd3dvbvdu9u93d29vN27273d3b273bvbu9vdvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile13\"\n    },\n    \"tile16\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9vdvbu73N27293b273N3cvb3du9283du9vd29u9zd3L2929u7vc3bvb3d3d3d3dy9vdu9vdu9u7273bu73bu8vbvdu7vb27u9u9vb29vb3L2729vb29u7vbvdu7vdu7y9vdu9vdu9u7293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile14\"\n    },\n    \"tile17\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273bu7u7vcvbzdi4ibu9y9u92Lh7u53L283YuHu7vcvbvdi4i7u8y8vN2LiLu7zLy73bu7u7vMvLzdu7u7u9y9u917m1u53L283Zu7m7vcvbvdu5u7tdy9vN27u7u73L273d3d3d3dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile15\"\n    },\n    \"tile18\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vGZmZmZmhri7iIiIiGZmuLxmZmZmaGa4u4aIiGaGZri8hmZmaGZouLuGZmaGZoa4vIZmZmZoZri7hmZmZoZmuLyGZmZmhma4u4aIiIiIZri8ZmZmZmZmuLuIiIiIiIi4vLu7u7u7u7u7vMzMvMzMvLy7u7u7u7u7uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile16\"\n    },\n    \"tile19\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3buLaGZmZmZmy4tmZoiIiIi7i2aGZmZmZsuLZmhmiIhou4uGZoZmZmjLi2hmaGZmaLuLZoZmZmZoy4tmaGZmZmi7i2ZoZmZmaMuLZoiIiIhou4tmZmZmZmbLi4iIiIiIiLu7u7u7u7u7y8zMvMzMvMy7u7u7u7u7uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile17\"\n    },\n    \"tile20\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vGZmZmZmhri7iIiIiGZmuLyIiIiIaGa4u93d3Y2IZri83d3d3YhouLvd3d3djYi4vN3d3d3diLi73d3d3d2NuLzd3d3d3d24u93d3d3d3bi83d3d3d3duLuIiIiIiIi4vLu7u7u7u7u7vMzMvMzMvLy7u7u7u7u7uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile18\"\n    },\n    \"tile21\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3buLaGZmZmZmy4tmZoiIiIi7i2aGiIiIiMuLZojd3d3du4uG2N3d3d3Li4jd3d3d3buL2N3d3d3dy4vd3d3d3d27i93d3d3d3cuL3d3d3d3du4vd3d3d3d3Li4iIiIiIiLu7u7u7u7u7y8zMvMzMvMy7u7u7u7u7uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile19\"\n    },\n    \"tile22\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d29u93dhtbdZmZm3d243W1mZmbW3bbdZmZmZmbdtmZmZmZmZta2ZmZmZmZm1rZmZmZmZmbWtmZmaJlpaNa2ZmZmmWlm1rZmZmiZaWjWtt1mZmZmZt243W1mZmbW3YbW3WZmZt3dy9vd3b273d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile20\"\n    },\n    \"tile23\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d29u93dhtbd3d3b3d2G1t3dvbvd3YbW3d3du93dhtbd3b3b3d2G1t293bvd3YbW3bu93d3dhta9u7273d2Glt27vd3d3YaW3b29u93dhpbd3b293d2G1t3dvbvd3YbW3d3d293dy9vd3b273d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile21\"\n    },\n    \"tile26\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273b3MzLzdvbzdzQAAwN29u93NAADA3b283c0AAMDdvbvdzQAAwN29vN3NAADA3b273b3MzLzdvbzd3d3d3d29u93du7vb3b283d2bm9vdvbvd3bu52929vN3dW1vb3b273d27u9vdvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile24\"\n    },\n    \"tile27\": {\n        \"data\": \"hwQQABAAAACwa2ZmZma2C7CLiIiIiLi7sItmZmZmuLuwa2ZmZmaIaLBrZmZmhoZmsGtmZmZohmawa2ZmhmaGZrBrZmZoZoZmsGtmhmZmhmawa2ZoZmaGZrBrhmZmZoZmsGtoZmZmhmawi4hoZmaGaLC7u7u7u7u7ALu7u7u7u7sAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile25\"\n    },\n    \"tile28\": {\n        \"data\": \"hwQQABAAAAC7293d3d3d3cvb3d3dvbvdu9vd3d29u93L293d3b273bvb3d3d3d3dy9vdvbvd3d272929u93d3cvb3b273d3du9vd3d3d3d3Lu93d3d3d3bu7293d3d3dsMu73d3d3d0Au7vb3d3d3QCwy7u7u7u7AAC7y5uZmcsAALC7AAAAsA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile26\"\n    },\n    \"tile29\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29u92727vb3b283bvbvd3dvbvdu9u93d29vN293b3d3b273b3du9vdvbzdvd272929u9293bvb3b283bvb3d3dvbvd3d3d3d27vN3d3d3dvbu73d3d3d27vAvd3d3dvbu7ALu7u7u7vAsAvJmZuby7AAALAAAAuwsAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile27\"\n    },\n    \"tile32\": {\n        \"data\": \"hwQQABAAAADMu7u7u727u8y8u7u727u7zMu7u7vbu7vMvLy7u7u9u8zLu7u7u9u9zLy8u7u7u9vAzMu7u7u7u8C8vLy7u7u7AMzLy7u7u7sAzLy8vLu7uwDAzMvLu7u7AADMvLy8u7sAAMDMy8vLuwAAAMzMvLy8AAAAAMzMzMwAAAAAAMzMzA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile30\"\n    },\n    \"tile33\": {\n        \"data\": \"hwQQABAAAAAAAAAAAMzMzAAAAADMzMzMAAAAzMy8vLwAAMDMy8vLuwAAzLy8vLy7AMDMy8u7u7sAzLy8vLu7uwDMy8u7u7u7wLy8vLu7u7vAzMu7u7u7u8y8vLu7u7vbzMu7u7u7273MvLu7u7u9u8zLu7u727u7zLy7u7vbu7vMu7u7u727uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile31\"\n    },\n    \"tile34\": {\n        \"data\": \"hwQQABAAAADMzMwAAAAAAMzMzMwAAAAAy8vLzMwAAAC7vLy8zAwAALu7y8vLzAAAu7u7vLzMDAC7u7vLy8vMALu7u7u8vMwAu7u7u8vLywy7u7u7u7zMDL27u7u7y8vM2727u7u7vMy727u7u8vLzLu7vbu7u7zMu7u9u7u7y8y7u9u7u7u7zA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile32\"\n    },\n    \"tile35\": {\n        \"data\": \"hwQQABAAAAC7u9u7u7u7zLu7vbu7u8vMu7u9u7u7vMy727u7u7vLzNu9u7u7u7zMvbu7u7vLy8y7u7u7u7zMDLu7u7vLy8sMu7u7u7y8zAC7u7vLy8vMALu7u7y8zAwAu8vLy8vMAAC7vLy8zAwAAMvLy8zMAAAAzMzMzAAAAADMzMwAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile33\"\n    },\n    \"tile39\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMzMzMzMzMzMu7u7u7u7u7vMzMzMzMzMzLu7u7u7u7u7u7u7u7u7u7u7u7u7u7u7uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile37\"\n    },\n    \"tile40\": {\n        \"data\": \"hwQQABAAAAC7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7vMzMzMzMzMzLu7u7u7u7u7zMzMzMzMzMwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile38\"\n    },\n    \"tile36\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273d3d3d3dvbzd3d3d3d29u93d3d3d3b283d3d3d3dvbvd3d3d3d29vN3d3d3d3b273d3d3d3dvbzd3d3d3d29u93d3d3d3b283d3d3d3dvbvd3d3d3d29vN3d3d3d3b273d3d3d3dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"bottomBlankTile\"\n    },\n    \"tile41\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3cvb3d3d3d3du9vd3d3d3d3L293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3cvb3d3d3d3du9vd3d3d3d3L293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"topBlankTile\"\n    },\n    \"tile42\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273cvMzNvbvbzdDAAA3Nu9u90MAADc27283QwAANzbvbvdDAAA3Nu9vN0MAADc27273QwAANzdvbzdDAAA3N29u90MAADc3b283QwAANzdvbvdDAAA3Nu9vN3LzMzb27273d3d3d3dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile34\"\n    },\n    \"tile45\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273d3d3d3dvbzu7u7u7u69u+4R7u7u7r286RkR7u7uvbuZGRER7u69vJ4ZERER7r27mRkRERHhvbzpGREREeG9u+4RERER4b287u4RERHhvbvd3d0REdG9vN3d3d0R0b273d3d3d3Rvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"clipboardTile\"\n    },\n    \"tile46\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273dfd3d2Zvbzd3d3dnZm5u93d3d2RZ7m8md3dHRF3lruZEZmZGXGWvJkZcZmZEZa7mZkRmZcXkbyZmRmRmXcRu5nd3Z2Zdxa83d3d3Zlnubvd3d3dnZm5vN3d3d3dmb273dfd3d3dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"beakerTile\"\n    },\n    \"tile47\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d1E3t3dy9vdTUTk3d27291ESETe3cvbTYREROTdu9tESIRERN7LS0RESERE5LtLRIREREREy9tERERExEu7201ERES8S8vb3URExLvUu9vdTUS8S93L293dxLvU3bvb3d29S93dy9vd3d3U3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"bookTile\"\n    },\n    \"tile48\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9tlxsxs1t2722URzGbW3cvbZWbMZtbdu9tlFsxm1t3L22URzGbW3bvbZcbMbNbdy9vd3d3dada7293d3Z2ZZsvbnWbdbflpu9uZadZtlpnL25af1t1m2bvbZpnZ3d3dy9ttlt3d3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"dvdsTile\"\n    },\n    \"tile13\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvbu7u73d3dy9u7u7vd3d2727u7u93d3cvbu7u73d3du9u7u7vdzd3L27u7u93M3bvb3d3dvczdy9u7u7vLy92724uIiLzL3cvbi4iHy8zdu9uLh4e8zN3L24uHh8vc3bvbi4iIzN3dy9u7u7vc3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"computerTile\"\n    },\n    \"tile44\": {\n        \"data\": \"hwQQABAAAADd3d3d3d2+vLvNu7u8u767u827u8vMvry7zcy7u7u+u7vbzbu7u768u7vNu7u7vru7u827u7u+vLu7zb67u767u9vN7rS7vry7zexORLu+u7vNu0REzL68u827u7y7vrvM+8zMz8y+vMz7zMz8/767zPvMzM/Mvrzd3d3d3d2+uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"closedBoxTile\"\n    },\n    \"tile49\": {\n        \"data\": \"hwQQABAAAADd3d3d3d2+vLvdzbu7vLu7u93Nu7vLzLy73c3Mu7u7u7vM/M+7u7u8u///z7u7u7u7///Pu7u7vLv//8+7u7u7u///z7u7u7y7/8/Mu7u7u7v/z7u7y8y8u//Pu7u8u7vM///MzM/MvPz//8zM/P+7zMz8zMzPzLzd3d3d3d2+uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"openBoxTile\"\n    },\n    \"tile50\": {\n        \"data\": \"hwQQABAAAABmZpaZlpmZmZaZZmaWmZmZlpmZmWZmlpmWmZmIlplmZmZmlliWmZmZlplmZpaZmYiWmZmZZmaWWJaZmZmWmWZmZmaWmYaYmZmWmWZmhpWZmYaYmZlmZpaZhpWZmZaZZmZmZpaZlpmZmZaZZmaWmZmZlpmZmWZmlpmWmZmZlplmZg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"damagedPanelLeft\"\n    },\n    \"tile51\": {\n        \"data\": \"hwQQABAAAACWmZmZlplmZpaZmZlmZpaZlplmZpaZmZlmZpaZlpmZmZaZmYiWmWZmlpmZWGZmlpmWmWZmlpmZiGZmlpmWmZlYlpmZmZaZZmaWmZmZZmaWmZaZZmaWmZmZZmaWmYaYmZmWmZmZhpVmZoaYmZlmZpaZhpVmZpaZmZlmZpaZlpmZmQ==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"damagedPanelRight\"\n    },\n    \"tile43\": {\n        \"data\": \"hwQQABAAAAD//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"spaceWalkTile\"\n    },\n    \"tile30\": {\n        \"data\": \"hwQQABAAAABmZpaZlpmZmZaZZmaWmZmZlpmZmWZmlpmWmZmZlplmZmZmlpmWmZmZlplmZpaZmZmWmZmZZmaWmZaZmZmWmWZmZmaWmZaZmZmWmWZmlpmZmZaZmZlmZpaZlpmZmZaZZmZmZpaZlpmZmZaZZmaWmZmZlpmZmWZmlpmWmZmZlplmZg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"solarPanelLeft\"\n    },\n    \"tile38\": {\n        \"data\": \"hwQQABAAAACWmZmZlplmZpaZmZlmZpaZlplmZpaZmZlmZpaZlpmZmZaZmZmWmWZmlpmZmWZmlpmWmWZmlpmZmWZmlpmWmZmZlpmZmZaZZmaWmZmZZmaWmZaZZmaWmZmZZmaWmZaZmZmWmZmZlplmZpaZmZlmZpaZlplmZpaZmZlmZpaZlpmZmQ==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"solarPanelRight\"\n    },\n    \"tile31\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGZmBgAAAAAAlplmZgYAAACWmZmZZmYGAJaZmZmWmWZmZmaWmZaZmZmWmWZmlpmZmZaZmZlmZpaZlpmZmZaZZmZmZpaZlpmZmZaZZmaWmZmZlpmZmWZmlpmWmZmZlplmZg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"solarPanelLeftEnd\"\n    },\n    \"tile37\": {\n        \"data\": \"hwQQABAAAACWmZmZlplmZpaZmZlmZpaZlplmZpaZmZlmZpaZlpmZmZaZmZmWmWZmlpmZmWZmlpmWmWZmlpmZmWZmlpmWmZmZlpmZmZaZZmaWmZmZZmYGAJaZZmYGAAAAZmYGAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"solarPanelRightEnd\"\n    },\n    \"tile12\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273bu7u9zdvbzdi4iIzN29u92Lh4fL3L283YuHh7zMvbvdi4iHy8y9vN2LiIi8y7273bu7u8vLvbzd3d3dvcy9u927u7vdzL283bu7u93Nvbvdu7u73d29vN27u7vd3b273bu7u93dvbzdu7u73d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"myTile10\"\n    },\n    \"tile52\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29ut3d3d3d3b273d3d3d3dvbzd3d3d3d29u93d3d3d3b283d3d3d3dvbvd3d3d3d29vN3d3d3d3b273d3d3d3dvbzd3d3d3d29u93d3d3d3b283d3d3d3dvbvd3d3d3d29vN3d3d3d3b273d3d3d3dvbrd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"bottomBlankTileCrew\"\n    },\n    \"tile25\": {\n        \"data\": \"hwQQABAAAADL293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3cvb3d3d3d3du9vd3d3d3d3L2727u7u7u7vb293d3d3dy7vd3d3d3d27293d3d3d3cvb3d3d3d3du9vd3d3d3d3L293d3d3d3bvb3d3d3d3dy9vd3d3d3d27293d3d3d3Q==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"spaceWalkTop\"\n    },\n    \"tile24\": {\n        \"data\": \"hwQQABAAAADd3d3d3d29vN3d3d3d3b273d3d3d3dvbzd3d3d3d29u93d3d3d3b283d3d3d3dvbu7u7u7u9u9vN3d3d3dvb273d3d3d3du7zd3d3d3d29u93d3d3d3b283d3d3d3dvbvd3d3d3d29vN3d3d3d3b273d3d3d3dvbzd3d3d3d29uw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"spaceWalkBottom\"\n    },\n    \"level6\": {\n        \"id\": \"level6\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAxMDAwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==\",\n        \"tileset\": [\n            \"myTiles.transparency16\"\n        ],\n        \"displayName\": \"blankTilemap\"\n    },\n    \"level4\": {\n        \"id\": \"level4\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAxZTAwMTQwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwNzE0MTQxNDFlMTQxNDE0MTQyODIwMTQwYjExMTIwMDAwMDcxNDE0MTQyYTE0MGIwMDAwMDAwMDAwMDAwODIyMTMxMzIxMDExMzIzMTMxMzEzMTMwYzExMTIwMDAwMDgyNDIzMDExMzIzMGMwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDYwNDA0MDMwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDUwNDBhMDAwMDAwMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDAwMDAyMDAwMDAwMDAwMDAwMDAwNzE0MDkxNDE0MWUxNDE0MTQxNDIwMTQxNDE0MmExNDFmMjAxNDE0MmExNDA5MTQyOTBiMDAwMDAwMDAwODEzMjIxMzEzMjExMzAxMjMxMzEzMjYyMzEzMTMxMzIzMTMxMzAxMTMxMzEzMjIxMzBjMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAyMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAyMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDA1MDQwNDBhMDAwMDExMTIwMDAwMDYwNDAzMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAyMDAwMDExMTIwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwNzFlMTQxNDE0MjAxNDE0MmExNDA5MTQwYjExMTIwMDA3MDkxNDE0MWUxZDE2MWIwMDAwMDAwMDAwMDAwODJiMTMyMzI3MTMxMzIzMTMxMzIyMTMwYzExMTIwMDA4MjIyNTIyMjExYzE1MWIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTgxNzE3MTcxNzE3MTcxNzBlMGQxYTFhMWExYTFhMWExYTE5MDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTgxNzE3MTcxNzE3MTcxNzBmMTAxYTFhMWExYTFhMWExYTE5MDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDExMTIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTgxNzE3MTcxNzE3MTcxNzBlMGQxYTFhMWExYTFhMWExYTE5MDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTgxNzE3MTcxNzE3MTcxNzBmMTAxYTFhMWExYTFhMWExYTE5MDAwMDAwMDAwMDIwMjIyMjIyMjIyMjIyMjIwMDIyMjIyMjIyMDIwMDIwMDAwMDAwMDAwMDAwMjAwMDAyMDAwMDAwMDIwMDIwMDAwMDAwMDAwMDAwMjAwMDAyMDAwMDAwMDIwMDIwMjIyMjAyMjIyMjIyMjIwMDIyMjIyMDIyMDIwMDAwMjAwMDAwMDIwMDAwMDAwMDAwMjAwMDIwMDAwMDIwMjIyMDIyMjIyMjIyMjIyMjIyMjIyMjIwMjIwMjIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMjIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMjIwMjIyMjIyMDIyMjIyMjIyMjIyMDIyMjIyMjIwMjAwMDAwMDAwMDIwMDIwMDAwMDAyMDAwMjAwMDAwMDIwMjIyMjIyMjIyMjIwMjIyMDAyMjIyMjAyMDAwMDIwMDAwMDAwMDAwMDAwMjAyMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMjAyMDAwMDAwMDAwMDAwMDIwMjIyMjIyMjIyMjIyMjIyMDIyMjIyMjAyMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile3\",\n            \"myTiles.tile5\",\n            \"myTiles.tile7\",\n            \"myTiles.tile8\",\n            \"myTiles.tile9\",\n            \"myTiles.tile10\",\n            \"myTiles.tile14\",\n            \"myTiles.tile15\",\n            \"myTiles.tile23\",\n            \"myTiles.tile27\",\n            \"myTiles.tile28\",\n            \"myTiles.tile29\",\n            \"myTiles.tile32\",\n            \"myTiles.tile33\",\n            \"myTiles.tile34\",\n            \"myTiles.tile35\",\n            \"myTiles.tile39\",\n            \"myTiles.tile40\",\n            \"myTiles.tile36\",\n            \"myTiles.tile41\",\n            \"myTiles.tile18\",\n            \"myTiles.tile19\",\n            \"myTiles.tile30\",\n            \"myTiles.tile31\",\n            \"myTiles.tile37\",\n            \"myTiles.tile38\",\n            \"myTiles.tile43\",\n            \"myTiles.tile24\",\n            \"myTiles.tile25\",\n            \"myTiles.tile11\",\n            \"myTiles.tile13\",\n            \"myTiles.tile16\",\n            \"myTiles.tile17\",\n            \"myTiles.tile26\",\n            \"myTiles.tile42\",\n            \"myTiles.tile44\",\n            \"myTiles.tile2\",\n            \"myTiles.tile45\",\n            \"myTiles.tile46\",\n            \"myTiles.tile47\",\n            \"myTiles.tile48\",\n            \"myTiles.tile1\",\n            \"myTiles.tile12\"\n        ],\n        \"displayName\": \"internationalSpaceStation\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile1 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile2 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile3 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile4 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile5 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile6 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile7 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile8 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile9 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile10 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile11 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile14 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile15 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile17 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile18 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile19 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile20 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile21 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile22 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile23 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile26 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile27 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile28 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile29 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile32 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile33 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile34 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile35 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile39 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile40 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile36 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile41 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile42 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile45 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile46 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile47 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile48 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile13 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile44 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile49 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile50 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile51 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile43 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile30 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile38 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile31 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile37 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile12 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile52 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile25 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile24 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"blankTilemap\":\n            case \"level6\":return tiles.createTilemap(hex`1000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`, img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`, [myTiles.transparency16], TileScale.Sixteen);\n            case \"internationalSpaceStation\":\n            case \"level4\":return tiles.createTilemap(hex`1e0014000000000000000000000000000000001112000000000000000000000000000000071414141e141414142820140b11120000071414142a140b0000000000000822131321011323131313130c111200000824230113230c000000000000000000000002000000000000001112000000000002000000000000000000000006040403000000000000001112000000000005040a0000000000000000000200000000000000000000111200000000000000020000000000000007140914141e14141414201414142a141f2014142a140914290b00000000081322131321130123131326231313132313130113131322130c00000000000000000000000200000000001112000000000200000000000000000000000000000000000504040a00001112000006040300000000000000000000000000000000000000000200001112000002000000000000000000000000071e1414142014142a1409140b111200070914141e1d161b000000000000082b132327131323131322130c11120008222522211c151b000000000000000000000000000000000000001112000000000000000000000000000000000000000000000000000000001112000000000000000000000000000000000000000018171717171717170e0d1a1a1a1a1a1a1a1900000000000000000000000018171717171717170f101a1a1a1a1a1a1a1900000000000000000000000000000000000000001112000000000000000000000000000000000000000018171717171717170e0d1a1a1a1a1a1a1a1900000000000000000000000018171717171717170f101a1a1a1a1a1a1a190000000000`, img`\n.222222222222222..222222222...\n.2.............2..2.......2...\n.2.............2..2.......2...\n.222222.22222222..2222.2222...\n...2....2............2...2....\n.222.2222222222222222222.2222.\n.2..........................2.\n.2..........................2.\n.22222222.22222222222.2222222.\n........2....2....2...2.......\n.22222222222.222.22.22222.....\n.2.............2.2............\n.2.............2.2............\n.222222222222222.22222222.....\n..............................\n..............................\n..............................\n..............................\n..............................\n..............................\n`, [myTiles.transparency16,myTiles.tile3,myTiles.tile5,myTiles.tile7,myTiles.tile8,myTiles.tile9,myTiles.tile10,myTiles.tile14,myTiles.tile15,myTiles.tile23,myTiles.tile27,myTiles.tile28,myTiles.tile29,myTiles.tile32,myTiles.tile33,myTiles.tile34,myTiles.tile35,myTiles.tile39,myTiles.tile40,myTiles.tile36,myTiles.tile41,myTiles.tile18,myTiles.tile19,myTiles.tile30,myTiles.tile31,myTiles.tile37,myTiles.tile38,myTiles.tile43,myTiles.tile24,myTiles.tile25,myTiles.tile11,myTiles.tile13,myTiles.tile16,myTiles.tile17,myTiles.tile26,myTiles.tile42,myTiles.tile44,myTiles.tile2,myTiles.tile45,myTiles.tile46,myTiles.tile47,myTiles.tile48,myTiles.tile1,myTiles.tile12], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n            case \"myTile\":\n            case \"tile1\":return tile1;\n            case \"myTile0\":\n            case \"tile2\":return tile2;\n            case \"myTile1\":\n            case \"tile3\":return tile3;\n            case \"myTile2\":\n            case \"tile4\":return tile4;\n            case \"myTile3\":\n            case \"tile5\":return tile5;\n            case \"myTile4\":\n            case \"tile6\":return tile6;\n            case \"myTile5\":\n            case \"tile7\":return tile7;\n            case \"myTile6\":\n            case \"tile8\":return tile8;\n            case \"myTile7\":\n            case \"tile9\":return tile9;\n            case \"myTile8\":\n            case \"tile10\":return tile10;\n            case \"myTile9\":\n            case \"tile11\":return tile11;\n            case \"myTile12\":\n            case \"tile14\":return tile14;\n            case \"myTile13\":\n            case \"tile15\":return tile15;\n            case \"myTile14\":\n            case \"tile16\":return tile16;\n            case \"myTile15\":\n            case \"tile17\":return tile17;\n            case \"myTile16\":\n            case \"tile18\":return tile18;\n            case \"myTile17\":\n            case \"tile19\":return tile19;\n            case \"myTile18\":\n            case \"tile20\":return tile20;\n            case \"myTile19\":\n            case \"tile21\":return tile21;\n            case \"myTile20\":\n            case \"tile22\":return tile22;\n            case \"myTile21\":\n            case \"tile23\":return tile23;\n            case \"myTile24\":\n            case \"tile26\":return tile26;\n            case \"myTile25\":\n            case \"tile27\":return tile27;\n            case \"myTile26\":\n            case \"tile28\":return tile28;\n            case \"myTile27\":\n            case \"tile29\":return tile29;\n            case \"myTile30\":\n            case \"tile32\":return tile32;\n            case \"myTile31\":\n            case \"tile33\":return tile33;\n            case \"myTile32\":\n            case \"tile34\":return tile34;\n            case \"myTile33\":\n            case \"tile35\":return tile35;\n            case \"myTile37\":\n            case \"tile39\":return tile39;\n            case \"myTile38\":\n            case \"tile40\":return tile40;\n            case \"bottomBlankTile\":\n            case \"tile36\":return tile36;\n            case \"topBlankTile\":\n            case \"tile41\":return tile41;\n            case \"myTile34\":\n            case \"tile42\":return tile42;\n            case \"clipboardTile\":\n            case \"tile45\":return tile45;\n            case \"beakerTile\":\n            case \"tile46\":return tile46;\n            case \"bookTile\":\n            case \"tile47\":return tile47;\n            case \"dvdsTile\":\n            case \"tile48\":return tile48;\n            case \"computerTile\":\n            case \"tile13\":return tile13;\n            case \"closedBoxTile\":\n            case \"tile44\":return tile44;\n            case \"openBoxTile\":\n            case \"tile49\":return tile49;\n            case \"damagedPanelLeft\":\n            case \"tile50\":return tile50;\n            case \"damagedPanelRight\":\n            case \"tile51\":return tile51;\n            case \"spaceWalkTile\":\n            case \"tile43\":return tile43;\n            case \"solarPanelLeft\":\n            case \"tile30\":return tile30;\n            case \"solarPanelRight\":\n            case \"tile38\":return tile38;\n            case \"solarPanelLeftEnd\":\n            case \"tile31\":return tile31;\n            case \"solarPanelRightEnd\":\n            case \"tile37\":return tile37;\n            case \"myTile10\":\n            case \"tile12\":return tile12;\n            case \"bottomBlankTileCrew\":\n            case \"tile52\":return tile52;\n            case \"spaceWalkTop\":\n            case \"tile25\":return tile25;\n            case \"spaceWalkBottom\":\n            case \"tile24\":return tile24;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
```

## Code Ninjas Game Building Session @showdialog
**International Space Station: Gorilla Suit Mini-Game!**
---
During Scott Kelly's year on the International Space Station, he worked with his twin brother Mark Kelly to play a prank on his fellow crew members.

Follow along with the steps of this tutorial to create a mini-game based on Scott Kelly's gorilla suit prank!

![project gif](https://github.com/Code-Ninjas-Home-Office/scott-kelly-games/blob/master/images/GorillaSuitMiniGame.gif?raw=true, "Gorilla Suit Mini Game project")
![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## Put Scott Kelly in a gorilla suit!

Add code to change the Scott Kelly Player sprite's image when it overlaps the gorilla suit box in the upper right part of the tilemap. 

- :function: In the coding area, find the ``||function:function gorillaGame||`` container.
- :paper plane: From ``||sprites:Sprites||`` drag the ``||sprites:set scottKellySprite image to||`` and ``||sprites:set scottKellySprite ghost through tiles||`` blocks into the container.
- :tree: From ``||scene:Scene||`` drag ``||scene:start screen effect||`` block underneath, then select a screen effect from the drop down.
- :lightbulb: Click the hint button below to see what your code should look like!

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
scottKellySprite.setImage(sk_images.gorillasuitRight)
scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, true)
effects.confetti.startScreenEffect()
let scottKellySprite: Sprite = null
```

```blocks
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
    scottKellySprite.setImage(sk_images.gorillasuitRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, true)
    effects.confetti.startScreenEffect()
}
let scottKellySprite: Sprite = null
```

## The Game Window 

As you add code to your project, look at the Game Window on the **lower right** of your screen to see it update! 

Be sure to playtest your game after each step of the tutorial!

![Game Window](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/GameWindow.png?raw=true "Game Window") 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## Scare the ISS Crew!

Code the gorilla-suited Scott Kelly sprite to scare his fellow crew members when they overlap.

- :paper plane: From ``||sprites:Sprites||`` drag the ``||sprites:on sprite overlaps otherSprite||`` container into the coding area, near the ``||functions(no click):function gorillaGame||`` container.
- :shuffle: This container already has an ``||logic(no click):if||`` **conditional** inside that will only scare Crew member sprites *if* Scott Kelly is wearing the gorilla suit.
- :paper plane: From ``||sprites:Sprites||`` drag ``||sprites:mySprite say||`` and ``||sprites:set mySprite ghost||`` into the ``||logic(no click):if||``.
- :mouse pointer: Drag the ``||variables(no click):otherSprite||`` bubble from the ``||sprites(no click):on sprite overlaps otherSprite||`` container to replace ``||variables(no click):mySprite||`` in those blocks.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
sprites.onOverlap(SpriteKind.Player, SpriteKind.Crew, function (sprite, otherSprite) {
    if (sprite.image.equals(sk_images.gorillasuitRight) || sprite.image.equals(sk_images.gorillasuitLeft)) {
    }
})
mySprite.sayText("Ahhhh! You scared me!")
mySprite.setFlag(SpriteFlag.Ghost, true)

let mySprite: Sprite = null

namespace SpriteKind {
    //% isKind
    export const Crew = SpriteKind.create()
}
```

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Crew, function (sprite, otherSprite) {
    if (sprite.image.equals(sk_images.gorillasuitRight) || sprite.image.equals(sk_images.gorillasuitLeft)) {
        otherSprite.sayText("Ahhhh! You scared me!")
        otherSprite.setFlag(SpriteFlag.Ghost, true)
    }
})
namespace SpriteKind {
    export const Crew = SpriteKind.create()
}
```

## Count the scared crew members!

Use a **variable** to keep track of how many crew members were scared! This number will show at the end of the game.

- :align justify: From ``||variables:Variables||`` drag ``||variables:set to 0||`` into the bottom of ``||functions(no click):function gorillaGame||`` then select ``||variables(no click):scareCount||`` from the drop down.
- :align justify: From ``||variables:Variables||`` drag ``||variables:change by 1||`` into the bottom of ``||logic(no click):if||`` then select ``||variables(no click):scareCount||`` from the drop down to increase the **variable** for each scared crew member.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
let scareCount = 0
scareCount += 1
```

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Crew, function (sprite, otherSprite) {
    if (sprite.image.equals(sk_images.gorillasuitRight) || sprite.image.equals(sk_images.gorillasuitLeft)) {
        otherSprite.sayText("Ahhhh! You scared me!")
        otherSprite.setFlag(SpriteFlag.Ghost, true)
        scareCount += 1
    }
})
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
    scottKellySprite.setImage(sk_images.gorillasuitRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, true)
    effects.confetti.startScreenEffect()
    scareCount = 0
}

let scottKellySprite: Sprite = null
let scareCount= 0
```

## Set a game timer!

Set a countdown timer that starts when Scott Kelly first puts on the gorilla suit, then ends 10 seconds later and removes the gorilla suit.

- :id card: From ``||info:Info||`` drag ``||info:start countdown||`` into the bottom of ``||functions(no click):function gorillaGame||``.
- :id card: From ``||info:Info||`` drag the entire ``||info:on countdown end||`` container into the coding area.
- :paper plane: From ``||sprites:Sprites||`` drag ``||sprites:set scottKellySprite image to||`` and ``||sprites:set scottKellySprite ghost through tiles||`` into the bottom of the ``||info(no click):on countdown end||`` container.
- :tree: From ``||scene:Scene||`` drag ``||scene:end screen effect||`` into the ``||info(no click):on countdown end||`` container.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
info.onCountdownEnd(function () {
    music.stopAllSounds()
    for (let value of sprites.allOfKind(SpriteKind.Crew)) {
        value.sayText("")
    }
})

scottKellySprite.setImage(sk_images.scottKellyRight)
scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, false)
effects.confetti.endScreenEffect()
info.startCountdown(10)

let scottKellySprite: Sprite = null
namespace SpriteKind {
    //% isKind
    export const Crew = SpriteKind.create()
}
``` 
```blocks
info.onCountdownEnd(function () {
    music.stopAllSounds()
    for (let value of sprites.allOfKind(SpriteKind.Crew)) {
        value.sayText("")
    }
    scottKellySprite.setImage(sk_images.scottKellyRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, false)
    effects.confetti.endScreenEffect()
})
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
    scottKellySprite.setImage(sk_images.gorillasuitRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, true)
    effects.confetti.startScreenEffect()
    scareCount = 0
    info.startCountdown(10)
}

let scottKellySprite: Sprite = null
let scareCount= 0
namespace SpriteKind {
    export const Crew = SpriteKind.create()
}
```

## Add mini-game directions!

Let the player know how to play the gorilla suit mini-game by adding additional directions!

- :circle: From ``||game:Game||`` drag ``||game:show long text||`` below the existing ``||game(no click):show long text||`` block inside ``||functions(no click):function gorillaGame||``.
- :mouse pointer: Click inside the white bubble to add instructions, such as "You have 10 seconds to scare as many crew members as possible!"
- :mouse pointer: Select ``||game(noclick):center||`` from the dropdown to match the placement of the other dialog box.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blocks
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
    game.showLongText("You have 10 seconds to scare as many crew members as possible!", DialogLayout.Center)
}
```

## Add background music!

Create some background music to enhance the mini-game!

- :headphones: From ``||music:Music||`` drag ``||music:play melody||`` underneath the ``||game(no click):show long text||`` block. 
- :mouse pointer: Click to open the melody editor, then select or create a melody to play during the mini-game. Adjust the tempo, or speed of the music, too.
- :headphones: Click ▼ then select ``||music(noclick):looping in background||`` so the sound effect plays throughout the mini-game.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blocks
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
    game.showLongText("You have 10 seconds to scare as many crew members as possible!", DialogLayout.Center)
    music.play(music.stringPlayable("C5 G A G B G A G ", 300), music.PlaybackMode.LoopingInBackground)
    scottKellySprite.setImage(sk_images.gorillasuitRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, true)
    effects.confetti.startScreenEffect()
    scareCount = 0
    info.startCountdown(10)
}

let scottKellySprite: Sprite = null
```

## Prevent Scott Kelly from exiting the ISS while dressed in the gorilla suit!

Prevent the Scott Kelly sprite from exiting the ISS during the gorilla suit mini-game!

- :tree: From ``||scene:Scene||`` drag 2 ``||scene:set wall at||`` blocks into the ``||functions(no click):function gorillaGame||`` container.
- :mouse pointer: Set both toggles to ``||loops(no click):<ON>||``. Set ``||scene(no click):col||`` to **23** in both blocks, and set ``||scene(no click):row||`` to **11** in one block and **12** in the other.
- :tree: Duplicate the 2 ``||scene(no click):set wall at||`` blocks then drag them into the ``||info(no click):on countdown end||`` container.
- :mouse pointer: Set both toggles on the duplicated blocks to ``||images(no click):<OFF>||``.


![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blocks
info.onCountdownEnd(function () {
    music.stopAllSounds()
    for (let value of sprites.allOfKind(SpriteKind.Crew)) {
        value.sayText("")
    }
    scottKellySprite.setImage(sk_images.scottKellyRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, false)
    effects.confetti.endScreenEffect()
    tiles.setWallAt(tiles.getTileLocation(23, 11), false)
    tiles.setWallAt(tiles.getTileLocation(23, 12), false)
})
function gorillaGame () {
    game.showLongText("My twin brother Mark sent me a gorilla suit to have some fun with the ISS crew!", DialogLayout.Center)
    game.showLongText("You have 10 seconds to scare as many crew members as possible!", DialogLayout.Center)
    music.play(music.stringPlayable("C5 G A G B G A G ", 300), music.PlaybackMode.LoopingInBackground)
    scottKellySprite.setImage(sk_images.gorillasuitRight)
    scottKellySprite.setFlag(SpriteFlag.GhostThroughTiles, true)
    effects.confetti.startScreenEffect()
    scareCount = 0
    info.startCountdown(10)
    tiles.setWallAt(tiles.getTileLocation(23, 11), true)
    tiles.setWallAt(tiles.getTileLocation(23, 12), true)
}

let scottKellySprite: Sprite = null
let scareCount= 0
namespace SpriteKind {
    export const Crew = SpriteKind.create()
}
```

## Congratulations!

Congratulations on completing the Scott Kelly Gorilla Suit mini game! 

![BTS Ninja Image](https://github.com/Code-Ninjas-Home-Office/scott-kelly-games/blob/master/images/BTS%20Ninja%20Image.png?raw=true "BTS Ninja Image") 

Click **Done** then give your project a title and click **Share Project** to create a shareable link to access your game!
