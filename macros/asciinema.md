<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
script:   https://cdn.jsdelivr.net/npm/asciinema-player@3.8.0/dist/bundle/asciinema-player.min.js
link:     https://cdn.jsdelivr.net/npm/asciinema-player@3.8.0/dist/bundle/asciinema-player.min.css

@asciinema: @asciinema_helper(@uid,``,@0)

@asciinema2: @asciinema_helper(@uid,`@0`,@1)

@asciinema_helper
<div id="id_@0"></div>
<script run-once modify="false">
  var _=AsciinemaPlayer.create('@2', document.getElementById('id_@0'),{@1});
</script>
@end
-->


# Asciinema
Embed an [asciinema](https://asciinema.org/) screencast.

## Usage


```
@[asciinema](test.cast)
```
Embeds the screencast `test.cast`.

```
@[asciinema2(`speed: 2, autoPlay:true, rows: 10`)](test.cast)
```

Embeds the screencast with some options passed to the Asciinema player.
For a complete list of available options see [here](https://docs.asciinema.org/manual/player/options/).