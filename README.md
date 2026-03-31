<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Monitor de Medios Corregido</title>
    <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
    <style>
        :root { --bg: #0d1117; --panel: #161b22; --border: #30363d; --accent: #58a6ff; }
        body { background: var(--bg); color: white; margin: 0; padding: 10px; font-family: sans-serif;
               display: grid; grid-template-columns: 350px 1fr 300px; height: 98vh; gap: 10px; overflow: hidden; }
        .panel { background: var(--panel); border: 1px solid var(--border); border-radius: 8px; display: flex; flex-direction: column; overflow: hidden; }
        .header { padding: 10px; background: #21262d; font-size: 12px; font-weight: bold; color: var(--accent); border-bottom: 1px solid var(--border); }
        
        /* Video Wall */
        .video-grid { display: grid; grid-template-columns: 1fr 1fr; grid-template-rows: 1fr 1fr; gap: 8px; }
        .v-card { background: #000; border: 1px solid var(--border); position: relative; }
        .v-card iframe { width: 100%; height: 100%; border: none; }

        /* Contenedores de contenido */
        .scroll-area { flex: 1; overflow-y: auto; padding: 5px; }
        .link-item { display: block; padding: 10px; color: #8b949e; text-decoration: none; border-bottom: 1px solid var(--border); font-size: 13px; }
        .link-item:hover { background: #30363d; color: white; }
    </style>
</head>
<body>

    <div class="panel">
        <div class="header">X LISTA: MONITOREO</div>
        <div class="scroll-area">
            <a class="twitter-timeline" data-theme="dark" data-chrome="noheader nofooter noborders" 
               href="https://twitter.com/i/lists/1529094396674641921?ref_src=twsrc%5Etfw">
               Cargando Tweets...
            </a>
        </div>
    </div>

    <div class="video-grid">
        <div class="v-card"><iframe src="https://www.youtube.com/embed/cb12KmMMDJA?enablejsapi=1&origin=http://localhost"></iframe></div>
        <div class="v-card"><iframe src="https://www.youtube.com/embed/SF06Qy1Ct6Y?enablejsapi=1&origin=http://localhost"></iframe></div>
        <div class="v-card"><iframe src="https://www.youtube.com/embed/DVZ2rJQb_0g?enablejsapi=1&origin=http://localhost"></iframe></div>
        <div class="v-card"><iframe src="https://www.youtube.com/embed/JrmCaXL5GZs?enablejsapi=1&origin=http://localhost"></iframe></div>
    </div>

    <div class="panel">
        <div class="header">GOOGLE TRENDS AR</div>
        <div class="scroll-area" id="trends-container">
            <script type="text/javascript" src="https://ssl.gstatic.com/trends_nrtr/3620_RC01/embed_loader.js"></script>
            <script type="text/javascript">
                try {
                    trends.embed.renderWidget("dailytrends", "", {
                        "geo": "AR",
                        "guestPath": "https://trends.google.com:443/trends/embed/"
                    });
                } catch (e) {
                    document.getElementById('trends-container').innerHTML = '<p style="padding:10px; font-size:12px;">Google bloqueó el acceso local. <a href="https://trends.google.com/trends/trendingsearches/daily?geo=AR" target="_blank" style="color:var(--accent)">Haz clic aquí para abrir en pestaña aparte.</a></p>';
                }
            </script>
        </div>
        
        <div class="header" style="border-top:1px solid var(--border)">ACCESOS DIRECTOS</div>
        <div class="scroll-area">
            <a href="https://www.lanacion.com.ar" target="_blank" class="link-item">La Nación</a>
            <a href="https://www.infobae.com" target="_blank" class="link-item">Infobae</a>
            <a href="https://www.clarin.com" target="_blank" class="link-item">Clarín</a>
            <a href="https://twitter.com/explore/tabs/trending" target="_blank" class="link-item">X Tendencias</a>
        </div>
    </div>

</body>
</html>
