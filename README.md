<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nostalgia</title>

<style>
    body {
        background: black;
        color: white;
        font-family: Arial;
        text-align: center;
        overflow: hidden;
        margin: 0;
    }

    h1 {
        margin-top: 40px;
        text-shadow: 0 0 10px red;
    }

    button {
        padding: 15px 25px;
        font-size: 18px;
        border: none;
        border-radius: 10px;
        margin: 20px;
        cursor: pointer;
        background: red;
        color: white;
        box-shadow: 0 0 15px red;
        transition: 0.2s;
    }

    button:hover {
        transform: scale(1.1);
    }

    /* Tremida + efeito hacker */
    .shake {
        animation: shake 0.3s infinite;
    }

    @keyframes shake {
        0% { transform: translate(0,0); }
        25% { transform: translate(5px,-5px); }
        50% { transform: translate(-5px,5px); }
        75% { transform: translate(5px,5px); }
        100% { transform: translate(0,0); }
    }

    .matrix {
        animation: matrix 0.8s infinite;
    }

    @keyframes matrix {
        0% { filter: hue-rotate(0deg); }
        50% { filter: hue-rotate(120deg); }
        100% { filter: hue-rotate(0deg); }
    }

    /* Glitter */
    .glitter {
        position: fixed;
        width: 8px;
        height: 8px;
        background: radial-gradient(white, transparent);
        pointer-events: none;
        animation: glitterAnim 0.7s linear forwards;
    }

    @keyframes glitterAnim {
        0% { opacity: 1; transform: scale(1); }
        100% { opacity: 0; transform: scale(3); }
    }

    #declaracaoBox {
        display: none;
        padding: 25px;
        text-align: left;
        font-size: 18px;
        margin: 20px;
        border-radius: 15px;
        background: rgba(255,255,255,0.1);
        box-shadow: 0 0 20px red;
    }
</style>
</head>
<body>

<h1>Nostalgia 🔥</h1>

<button id="btnNostalgia">Nostalgia</button>
<button id="btnDeclaracao">Declaração Especial</button>

<div id="declaracaoBox"></div>

<!-- Sons -->
<audio id="somAlerta" src="https://cdn.pixabay.com/audio/2022/03/15/audio_9b0e1d1298.mp3"></audio>
<audio id="somGlitch" src="https://cdn.pixabay.com/audio/2021/08/04/audio_d78b810e52.mp3"></audio>

<script>
    const btnN = document.getElementById("btnNostalgia");
    const somAlerta = document.getElementById("somAlerta");
    const somGlitch = document.getElementById("somGlitch");

    btnN.addEventListener("click", () => {
        somAlerta.play();
        somGlitch.play();

        document.body.classList.add("shake");
        document.body.classList.add("matrix");

        setTimeout(() => {
            window.location.href = "https://wa.me/5582981935615";
        }, 2000);
    });

    /* Glitter animado ao toque */
    document.addEventListener("mousemove", (e) => {
        const g = document.createElement("div");
        g.classList.add("glitter");
        g.style.left = e.pageX + "px";
        g.style.top = e.pageY + "px";
        document.body.appendChild(g);

        setTimeout(() => g.remove(), 700);
    });

    /* Botão da declaração */
    document.getElementById("btnDeclaracao").onclick = () => {
        const box = document.getElementById("declaracaoBox");

        box.style.display = "block";

        box.innerHTML = `
        <h2>💌 Minha declaração pra você</h2>
        <p>
        Eu sei que eu não sou o cara mais fácil do mundo... sou vaqueiro, vida corrida,
        cabeça dura, meu tempo é bagunçado, eu erro, deixo a desejar, às vezes pareço frio.
        Mas a verdade é que eu sinto tudo de um jeito que não sei demonstrar.
        </p>
        <p>
        A distância machuca, a saudade pesa, e eu fico tentando esconder o quanto eu te quero bem,
        só pra não parecer fraco. Mas você sempre foi minha força. Você trouxe luz num momento que
        eu só via escuridão. Você foi meu respiro quando o mundo parecia apertado demais.
        </p>
        <p>
        Eu não sou perfeito, mas sou seu. Eu tento, eu erro, eu caio, mas volto… sempre volto,
        porque é você quem faz tudo valer a pena. Eu sinto falta do seu jeito, da sua voz,
        da paz que você me dá mesmo longe.
        </p>
        <p>
        Se eu pudesse, encurtava essa distância agora. Te puxava pra perto, te colocava nos braços
        e mostrava aquilo que às vezes eu não consigo dizer: você é minha escolha. Sempre foi.
        </p>
        <p>
        Obrigado por aguentar minhas falhas, meu silêncio, minhas tempestades.
        Eu te amo do meu jeito torto, mas é amor de verdade.
        </p>
        `;
    };
</script>

</body>
</html>
