<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
script:   https://cdn.jsdelivr.net/npm/asciinema-player@3.8.0/dist/bundle/asciinema-player.min.js
link:     https://cdn.jsdelivr.net/npm/asciinema-player@3.8.0/dist/bundle/asciinema-player.min.css

@asciinema: @asciinema_helper(@uid,@0,@1)

@asciinema_helper
<div id="id_@0"></div>
<script run-once modify="false">
  var _=AsciinemaPlayer.create('@2', document.getElementById('id_@0'),@1);
</script>
@end

@embed
<script run-once modify="false">
fetch("@1")
  .then(response => {
    if (!response.ok) {
      const error = `HTTP error! status: ${response.status}`
      send.lia(error)
      throw new Error(error);
    }
    return response.text();
  })
  .then(html => {
    html = html.split('')

    for(let i=0; i<html.length; i++) {
      if (html[i] === '"') {
        html[i] = "'"
      }
    }

    send.lia(`HTML: <iframe @0 srcdoc="${html.join('')}"></iframe>`)
  })
  .catch(error => {
    console.warn('Error fetching and extracting text:', error);
    send.lia(error)
  });

"LIA: wait"
</script>
@end

-->

# Macros