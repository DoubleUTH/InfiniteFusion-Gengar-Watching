# InfiniteFusion-Gengar-Watching

Steps:
1. Go to the game directory and open "Data/Scripts/003_Game processing/002_Scene_Map.rb" with a text editor
2. Add the following at the end of the file.
```ruby
class GengarWatching
  def initialize
    bitmap = pbBitmap("Graphics/Pictures/031b")
    viewport = Viewport.new(0, Graphics.height - bitmap.height, bitmap.width, bitmap.height)
    @sprite = Sprite.new(viewport)
    @sprite.bitmap = bitmap
  end

  def dispose
    @sprite.dispose if !pbDisposed?(@sprite)
  end
end
```
3. Add a line under `createSpritesets` in `def main`.
```ruby
@gengarWatching = GengarWatching.new
```
4. Add a line under `dispose` in `def main`.
```ruby
@gengarWatching.dispose
```
5. Run the game. Gengar is now permanently watching you.

This should be the final code after the modifications.

<img width="796" height="635" alt="Screenshot 2026-04-20 024624" src="https://github.com/user-attachments/assets/64325234-2703-447a-a51a-e21b52198e41" />
