[index.html](https://github.com/user-attachments/files/28778387/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Player Aleatório</title>
</head>
<body>
    <video id="player" width="640" height="360" controls autoplay muted></video>

    <script>
        // Sua playlist: pode ter mp4 locais e links .m3u8
        const lista = [
            "https://cdn.vod.br1.jmvstream.com/vod/vod_20775/f/2qvxnoex044t2jm/h/4/playlist.m3u8?uf085lum5fbz=gr3iopaw27dh1eyh.mp4",
            "https://cdn.vod.br1.jmvstream.com/vod/vod_20775/f/2qvxnoex044t2jm/h/4/playlist.m3u8?uf085lum5fbz=gr3iopaw27dh1eyh.mp4",
            "https://cdn.vod.br1.jwstream.com/vod/vod_20775/f/2qvxnoe044tzjm4/h/4/playlist.m3u8?uf8851um5fbz=gr3iop"
        ];

        const player = document.getElementById("player");

        // Função para escolher vídeo aleatório
        function proximoVideo() {
            let novoIndice;
            do {
                novoIndice = Math.floor(Math.random() * lista.length);
            } while (player.src.includes(lista[novoIndice])); // evita repetir o mesmo vídeo seguido

            player.src = lista[novoIndice];
            player.play();
        }

        // Começa com um vídeo aleatório
        proximoVideo();

        // Quando terminar, escolhe outro aleatório
        player.addEventListener("ended", proximoVideo);
    </script>
</body>
</html>
