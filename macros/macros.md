<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de

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