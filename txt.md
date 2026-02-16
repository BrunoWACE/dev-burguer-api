<!-- Passo a Passso

Passo 01
Para instalar o pnpm
comando: npm install -g pnpm

Passo 02
Para adicionar o express
comando: pnpm add express

Passo 03
Criar uma pasta chamada: src
source => origem

Criar um arquivo dentro da pasta src chamado: app.js
digite esse código:
import express from 'express';

const app = express();

export default app;


Passo 04
Criar um arquivo dentro da pasta src chamado: server.js
digite esse código:
import app from "./app.js";

app.listen(3001, () => console.log("Application is running at port 3001"))

Passo 05
Iremos rodar nossa aplicação, no terminal usaremos o seguinte código:
node src/server.js

mas antes vá até o package.json e altere essa linha de códifo:
antiga:  "type": "commonjs",
Nova:  "type": "module",

assim o código 'node src/server.js' irá funcionar corretamente.
OBS: Para para a aplicação Ctrl+C

Podemos configurar um atalho para facilicar na hora de iniciar nossa aplicação
em package.json procure por "scripts"
código original:
 "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },

  código modificado:
    "scripts": {
    "dev": "node src/server.js"
  },

  agora podemos abrir nossa aplicação assim: 'pnpm dev'

  Para não termos problemas futuros iremos modificar nosso main também
  original:   "main": "index.js",
  modificado: "main": "node src/server.js",

  Iremos configurar para sempre que realizamos uma atualização o mesmo seja refletido automaticamente
  para isso precisamos modificar nosso script veja:
  original:
   "scripts": {
    "dev": "node src/server.js"
  },

  modificado:
   "scripts": {
    "dev": "node --watch src/server.js"
  },

  ----------------------------------------------------------------------------------
Passo 06
>Instalar o Biome.js - ferramenta de padronização de código

no terminal:
pnpm add -D -E @biomejs/biome

agora vamos configurar ele
no terminal:
pnpm exec biome init

iriemos realizar algumas modificações:

código original:
	"formatter": {
		"enabled": true,
		"indentStyle": "tab"
	},

    Código mnodificado:
    	"formatter": {
		"enabled": true,
		"indentStyle": "space"
        },

Outra linha que precisa ser modificada
        código original:
        	"javascript": {
		"formatter": {
			"quoteStyle": "double"
		}
	},

    código modificado:
    	"javascript": {
		"formatter": {
			"quoteStyle": "single"
		}
	
	},

    OBS: Caso não tenha instalado instale a extensão Biome

    configuração rapida para converter "" para ''
    Ctrl + Shift + P
    digite: >open user settings (JSON)
    cole o código:
       "[javascript]": {
        "editor.defaultFormatter": "biomejs.biome"
    },
    "[typescript]": {
        "editor.defaultFormatter": "biomejs.biome"
    },
    "editor.formatOnSave": true

    Iremos mandar tudo para o github menos o node_modules
    então ireimos criar um arquivo chamado: .gitignore
    e dentro do arquivo vamos escrever o que queremos ignorar: node_modules
    pronto tudo certo.





