<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de


@pyconsole 
<a target="_blank" role="button" href="https://tilman-schieber.github.io/console"><button class="lia-btn lia-btn--outline">Python Konsole</button></a>
@end


@lialink
<script modify="false" run-once="true">
`LIASCRIPT: [@0](${window.location.origin + window.location.pathname}?@1)`
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

## Lialink

Example:

`@[lialink(relative)](dir/french.md)`
@[lialink(relative)](dir/french.md)


## Embed

`@[embed(style="height: 400px; width:600px; border: none")](html/5/listslicer.html)`