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
    <meta name="google-site-verification" content="foN88DTqzWXIAdJPP2mPofvdzuOBZ5Ch5rguMVmEjqo" />
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
            <p id="totalpecas1">Total de Pe??as: <input type="number" name="totalpecas" id="totalpecas"></p>
            <input type="button" value="Calcular" onclick="calcular()" id="button">
        </div>
        <div id="msg">
            <p id='espessura3'></p>
            <p id='placas'></p>
           
            
            
            
        </div>
        <p id="inst">
            <p id="step1">
                <p id="p1Esp"></p>
                <p id="p2Esp"></p>
            </p>

            <p id="step2">
                <p id="foto"></p>
                <p id="p1Comp"></p>
                <p id="p2Comp"></p>
            </p>
            
            <p id="step3">
                <p id="corteLarg"></p>
            </p>
            <p id="step4">
                <p id="retLarg"></p>
            </p>
            <p id="step5">

            </p>
            <p id="step6">
                <p id="corteComp"></p>
            </p>
            <div>
                <p id="endCheck">
                    <p id="endLarg"></p>
                    <p id="endEsp"></p>
                    <p id="endComp"></p>
                    <p id="endPed"></p>
                </p>
            </div>
        </p>
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
            const realEspessura = [5.3, 7.3, 8.3, 10.3]
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
            var restoLargura = 0

        
            

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
        corteLargura = comprimentoPlaca / pecaPorPlaca
        
        
        

        /*discoLargura = (Math.floor(resLarguraPeca / 1.5))
        pecaPorPlaca = (pecaPorPlaca * discoLargura)*/
        pecaPorPlaca = Math.floor(comprimentoPlaca / (resLarguraPeca + 1))
        totalPlacas = (resPedido + adicionalPecas) / pecaPorPlaca
        
        window.document.getElementById('placas').innerHTML="Voc?? vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!" 
        
        window.document.getElementById("inst").innerHTML="<strong>Instru????es</strong>"     

        window.document.getElementById("step1").innerHTML="<strong>Passo 1: Espessura</strong>"
        
        for(i = 0;i < realEspessura.length;i++){
            if (resEspessura > 0 && resEspessura <= 5) {
                var p1Esp = ((realEspessura[0] - resEspessura)/2)
                
                window.document.getElementById("p1Esp").innerHTML="Primeira Passada:<br>" + (resEspessura + p1Esp) 
                window.document.getElementById("p2Esp").innerText="Segunda Passada:" + resEspessura
                
            } else if(resEspessura > 0 &&resEspessura <= 7){
                var p1Esp = ((realEspessura[1] - resEspessura)/2)
                
                window.document.getElementById("p1Esp").innerHTML="Primeira Passada:<br>" + (resEspessura + p1Esp) 
                window.document.getElementById("p2Esp").innerText="Segunda Passada:" + resEspessura
                
            }else if (resEspessura > 0 &&resEspessura <= 8){
                var p1Esp = ((realEspessura[2] - resEspessura)/2)
                
                window.document.getElementById("p1Esp").innerHTML="Primeira Passada:<br>" + (resEspessura + p1Esp) 
                window.document.getElementById("p2Esp").innerText="Segunda Passada:" + resEspessura
                
            }else if (resEspessura > 0 &&resEspessura <= 10){
                var p1Esp = ((realEspessura[3] - resEspessura)/2)
                
                window.document.getElementById("p1Esp").innerHTML="Primeira Passada:<br>" + (resEspessura + p1Esp) 
                window.document.getElementById("p2Esp").innerText="Segunda Passada:" + resEspessura
            }else{
                document.getElementById('p1Esp').innerHTML="Espessura da Placa - Valor digitado incorreto!"
                
            }
        }
        
        
        window.document.getElementById("step2").innerHTML="<strong>Passo 2: Retifica????o Comprimento</strong>"

        var img = document.createElement("img")
        img.src = "placalargurared.jpeg"

        
        document.getElementById("foto").appendChild(img)
        
    

        window.document.getElementById("p1Comp").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1) 

        window.document.getElementById("p2Comp").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada 

        window.document.getElementById("step3").innerHTML="<strong>Passo 3: Corte Largura</strong>"
            if((corteLargura - resLarguraPeca) > 3){
                window.document.getElementById("corteLarg").innerHTML="Regulagem do corte:" + (resLarguraPeca + 0.50)
            } else{
                window.document.getElementById("corteLarg").innerHTML="Regulagem do corte:" + corteLargura
            }

        window.document.getElementById("step4").innerHTML="<strong>Passo 4: Retifica????o Largura</strong>"
        window.document.getElementById("retLarg").innerHTML="Largura da Pe??a:" + resLarguraPeca    

        window.document.getElementById("step5").innerHTML="<strong>Passo 5: Quebrar os cantos</strong>"

        window.document.getElementById("step6").innerHTML="<strong>Passo 6: Corte Comprimento</strong>"
        window.document.getElementById("corteComp").innerHTML="Comprimento da Pe??a:" + resComprimentoPeca     
        
        
        window.document.getElementById("endCheck").innerHTML="<strong>Checagem Final</strong>"
        window.document.getElementById("endLarg").innerHTML="Largura da Pe??a:" + resLarguraPeca
        window.document.getElementById("endEsp").innerHTML="Espessura da Pe??a:" + resEspessura
        window.document.getElementById("endComp").innerHTML="Comprimento da Pe??a:" + resComprimentoPeca
        window.document.getElementById("endPed").innerHTML="Total Pe??as:" + resPedido
           
            
        

        
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
        window.document.getElementById('placas').innerHTML="Voc?? vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!" 
        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1)  
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada

    }else if(resComprimentoPeca > 14.7 && resComprimentoPeca < 17.5){
        pecaPorPlaca = Math.floor(testeC2) 
        discoComprimento = (Math.ceil(testeC2 / 2))
        corteComprimento = pecaPorPlaca * resComprimentoPeca + 0,20 + discoComprimento
        restoComprimento = larguraPlaca - corteComprimento
        primeiraPassada = corteComprimento + (restoComprimento / 2)
        segundaPassada = corteComprimento + 0,15

         /*discoLargura = (Math.floor(resLarguraPeca / 1.5))
        pecaPorPlaca = (pecaPorPlaca * discoLargura)*/
        pecaPorPlaca = Math.floor(comprimentoPlaca / (resLarguraPeca + 1)) * 2
        totalPlacas = (resPedido + adicionalPecas) / pecaPorPlaca

        window.document.getElementById('placas').innerHTML="Voc?? vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!"
        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1) 
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada 
        window.document.getElementById("pag2").innerHTML="Clique aqui para ver o passo a passo:" 

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


        window.document.getElementById('placas').innerHTML="Voc?? vai precisar de" + ' ' + Math.ceil(totalPlacas) + ' ' + "placas!"
        window.document.getElementById("passada1").innerHTML="Primeira passada comprimento:" + ' ' + primeiraPassada.toFixed(1) 
        window.document.getElementById("passada2").innerHTML="Segunda passada comprimento:" + ' ' + segundaPassada
    }else{
        window.document.getElementById('placas').innerHTML="Valor digitado incorreto!"
    }
    }
    

    </script>
</body>
</html>
