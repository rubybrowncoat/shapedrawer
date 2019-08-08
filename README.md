# Shape Drawer

---

Draws simple shapes like libgdx's ShapeRenderer does, but uses a Batch to perform the drawing.

Comes with overloaded methods to draw lines, paths, ellipses, regular polygons and rectangles.
Since it uses a Batch to perform the drawing, it can be used in between `Batch#begin()` and `Batch#end()` without
needing to flush the Batch.

Just needs to be provided with a Batch (SpriteBatch or PolygonSpriteBatch will work) and a TextureRegion.

---


## Usage

To create a ShapeDrawer instance you just need a Batch and a TextureRegion. Typically this is a single white pixel so that you can easily colour it,
and this is best packed into an atlas with your other textures. However for testing purposes you can make one programmatically:

```java   
Pixmap pixmap = new Pixmap(1, 1, Format.RGBA8888);
pixmap.setColor(Color.WHITE);
pixmap.drawPixel(0, 0);
texture = new Texture(pixmap);
pixmap.dispose();
TextureRegion region = new TextureRegion(texture, 0, 0, 1, 1);
```

Then instantiate a ShapeDrawer:

```java
ShapeDrawer drawer = new ShapeDrawer(batch, region);
```

To use it, simply call its drawing methods in between `Batch.begin()` and `Batch#end()`. Something like this:

```java
batch.begin();
drawer.line(0,0,100,100);
batch.end();
```

That's it!


---

Test application uses the [Commodore 64 UI Skin](https://ray3k.wordpress.com/artwork/commodore-64-ui-skin-for-libgdx/) created by Raymond "Raeleus" Buckley under the [CC BY license](https://creativecommons.org/licenses/by/4.0/), check out the others!
