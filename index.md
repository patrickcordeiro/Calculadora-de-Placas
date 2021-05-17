<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet">

    <style>


        body{
            background-color: goldenrod;
        
        
        
        }
        section{
            background-color: white;
            border-radius: 10px;
            padding: 15px;
            width: 500px;
            margin: auto;
            margin-top: 5px;
            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.459);
        }
        div#entrada{
            width: 500px;
            height: auto;
            padding-right: 10px;
            padding-left: 10px;
            text-align: center;
            justify-content: center;
            align-items: center;
        }
        footer{
            padding: 30px;
            width: 500px;
            margin: auto;
            font-size: 12pt;
            color: white;
        }
        button {
            font-size: 12pt;
            padding: 30px;
            width: 500px;
            margin: auto;
            background-color: gray;
            color: white;
            border-radius: 10px;
            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.39);
        
        }
        h1{
            text-align: center;
            border: double;
            background-color: gray;
            color: white;
            width: 500px;
            margin: auto;
            margin-top: 100px;
        
        }
        p{
            text-align: center;
            font-size: x-large;
        }
        #produced{
            font-family: 'Dancing Script', cursive;
        
        }
    </style>
    
    <title>Calculadora de Placas</title>
</head>
<body>
    <header>
        <h1>Calculadora de Placas</h1>
    </header>

    <section>
        <div id="entrada">
            <p id="espessura1">Espessura: <input type="number" name="esp" id="esp"></p>
            <p id="largura1">Largura: <input type="number" name="largura" id="largura"></p>
            <p id="comprimento1">Comprimento: <input type="number" name="comprimento" id="comprimento"></p>
            <p id="totalpecas1">Total de Peças: <input type="number" name="totalpecas" id="totalpecas"></p>
            <input type="button" value="Calcular" onclick="calcular()" id="button">
        </div>
        <div id="msg">
            <p id='espessura3'></p>
            <p id='placas'></p>
            <p id="passada1"></p>
            <p id="passada2"></p>
        </div>
    </section>

    <footer>
        <p id='agradecimento' style='display:none'>Obrigado por utilizar nossa calculadora de placas!</p>
        
        <p id="produced">Desenvolvido por Patrick Cordeiro</p>
        <div id="area">
            <button type="button" onclick="document.getElementById('agradecimento').style.display='block'">Finalizar!</button>
        </div>
    </footer>

    <script>
        function calcular() {
            const espessuraPlacas = [5, 7, 8, 10]
            const comprimentoPlaca = 47
            const larguraPlaca = 37
            const adicionalPecas = 30
            var totalPlacas = 0
            var restoComprimento = 0
            var primeiraPassada = 0
            var segundaPassada = 0
            var discoComprimento = 0
            var discoLargura = 0
            var pecaPorPlaca = 0
            var corteComprimento = 0
            var corteLargura = 0
            var totalPecas = 0
            

            var espessura = window.document.getElementById('esp')
            var resEspessura = Number(espessura.value)
            var larguraPeca = window.document.getElementById('largura')
            var resLarguraPeca = Number(larguraPeca.value)
            var comprimentoPeca = window.document.getElementById('comprimento')
            var resComprimentoPeca = Number(comprimentoPeca.value)
            var testeC1 = comprimentoPlaca / resComprimentoPeca;
            var testeC2 = larguraPlaca / resComprimentoPeca;
            var testeL1 = comprimentoPlaca / resLarguraPeca;
            var testeL2 = larguraPlaca / resLarguraPeca;
            var pedido = window.document.getElementById('totalpecas')
            var resPedido = Number(pedido.value)
            
            for(i = 0;i < espessuraPlacas.length;i++){
            if (resEspessura > 0 && resEspessura <= 5) {
                document.getElementById('espessura3').innerHTML="Espessura da Placa - Use a placa de" + ' ' + espessuraPlacas[0]
                
            } else if(resEspessura > 0 &&resEspessura <= 7){
                document.getElementById('espessura3').innerHTML="Espessura da Placa - Use a placa de" + ' ' + espessuraPlacas[1]
                
            }else if (resEspessura > 0 &&resEspessura <= 8){
                document.getElementById('espessura3').innerHTML="Espessura da Placa - Use a placa de" + ' ' + espessuraPlacas[2]
                
            }else if (resEspessura > 0 &&resEspessura <= 10){
                document.getElementById('espessura3').innerHTML="Espessura da Placa - Use a placa de" + ' ' + espessuraPlacas[3]
            }else{
                document.getElementById('espessura3').innerHTML="Espessura da Placa - Valor digitado incorreto!"
                
            }
        
    }


            if (resComprimentoPeca > 22.5 && resComprimentoPeca < 36){
        pecaPorPlaca = 1
        discoComprimento = 0
        corteComprimento = resComprimentoPeca
        
        restoComprimento = larguraPlaca - corteComprimento
        primeiraPassada = corteComprimento + (restoComprimento / 2)
        segundaPassada = corteComprimento

        /*discoLargura = (Math.floor(resLarguraPeca / 1.5))
        pecaPorPlaca = (pecaPorPlaca * discoLargura)*/
        pecaPorPlaca = Math.floor(comprimentoPlaca / (resLarguraPeca + 1))
        totalPlacas = (resPedido + adicionalPecas) / pecaPorPlaca
        
        window.document.getElementById('placas').innerHTML="Você vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!" 
        

        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1) 
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada
        

        
    }else if(resComprimentoPeca >= 17.6 && resComprimentoPeca <= 22.5){
        pecaPorPlaca = Math.floor(testeC1)
        discoComprimento = testeC1 / 2
        corteComprimento = pecaPorPlaca * resComprimentoPeca + 0,20 + discoComprimento
        restoComprimento = comprimentoPlaca - corteComprimento
        primeiraPassada = corteComprimento + (restoComprimento / 2)
        segundaPassada = corteComprimento + 0,15
         /*discoLargura = (Math.floor(resLarguraPeca / 1.5))
        pecaPorPlaca = (pecaPorPlaca * discoLargura)*/
        pecaPorPlaca = Math.floor(larguraPlaca / (resLarguraPeca + 1)) * 2
        totalPlacas = (resPedido + adicionalPecas) / pecaPorPlaca
        window.document.getElementById('placas').innerHTML="Você vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!" 
        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1)  
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada

    }else if(resComprimentoPeca > 14.7 && resComprimentoPeca < 17.5){
        pecaPorPlaca = Math.floor(testeC2) 
        discoComprimento = (Math.ceil(testeC2 / 2))
        corteComprimento = (pecaPorPlaca * resComprimentoPeca) + discoComprimento + 0.15
        restoComprimento = larguraPlaca - corteComprimento
        primeiraPassada = corteComprimento + (restoComprimento / 2)
        segundaPassada = corteComprimento

         /*discoLargura = (Math.floor(resLarguraPeca / 1.5))
        pecaPorPlaca = (pecaPorPlaca * discoLargura)*/
        pecaPorPlaca = Math.floor(comprimentoPlaca / (resLarguraPeca + 1)) * 2
        totalPlacas = (resPedido + adicionalPecas) / pecaPorPlaca

        window.document.getElementById('placas').innerHTML="Você vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!"
        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1) 
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada 

    }else if(resComprimentoPeca >= 12 &&  resComprimentoPeca <= 14.7) {
        pecaPorPlaca = Math.floor(testeC1) 
        discoComprimento = (Math.ceil(testeC1 / 2))
        corteComprimento = (pecaPorPlaca * resComprimentoPeca) + discoComprimento + 0.15  
        restoComprimento = comprimentoPlaca - corteComprimento
        primeiraPassada = corteComprimento + (restoComprimento / 2)
        segundaPassada = corteComprimento 

         /*discoLargura = (Math.floor(resLarguraPeca / 1.5))
        pecaPorPlaca = (pecaPorPlaca * discoLargura)*/
        pecaPorPlaca = Math.floor(larguraPlaca / (resLarguraPeca + 1)) * 3
        totalPlacas = (resPedido + adicionalPecas) / pecaPorPlaca


        window.document.getElementById('placas').innerHTML="Você vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!"
        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1) 
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada
    }else{
        window.document.getElementById('placas').innerHTML="Valor digitado incorreto!"
    }
    }
    

    </script>
</body>
</html>
