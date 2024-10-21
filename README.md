<!--

script:  https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js

@h5p_embed: @h5p_embed_(@uid,@0)

@h5p_embed_
<iframe id="h5p_@0" style="width:100%;" srcdoc='<!DOCTYPE html><html lang="de"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><style>body{display:flex;justify-content:center;align-items:center;height:100vh;margin:0;background-color:#f0f0f0}.loader{border:16px solid #f3f3f3;border-top:16px solid #3498db;border-radius:50%;width:80px;height:80px;animation:spin 2s linear infinite}@keyframes spin{0%{transform:rotate(0deg)}100%{transform:rotate(360deg)}}</style></head><body><div class="loader"></div></body></html>'></iframe>
<script run-once>
fetch('@1')
    .then(response => {
        if (!response.ok) {
            throw new Error('Netzwerkantwort war nicht ok ' + response.statusText);
        }
        return response.text(); // Abruf als Text
    })
    .then(htmlText => {
        document.getElementById('h5p_@0').srcdoc = htmlText;
        send.lia("LIA: stop");
    })
    .catch(error => {
        console.error('Es gab ein Problem mit dem Abruf: ', error);
        send.error("LIA: stop");
    });

"LIA: wait"
</script>
@end

-->

# H5P-embed
<!-- 
persistent: true
-->

@[h5p_embed](h5p/juxt.html)


## virtual-embed
<!-- 
persistent: true
-->

@[h5p_embed](h5p/virtual-tour-360.html)