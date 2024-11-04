import React from 'react';
import { Text, StyleSheet } from 'react-native';

export default function Texto({ children, style }) {
  let estilo = estilos.texto;
  
  if(style?.fontWeight === 'bold') {
    estilo = estilos.textoNegrito;
  }

  return <Text style={[style, estilo]}>{ children }</Text>
}

const estilos = StyleSheet.create({
  texto: {
    fontFamily: 'MontserratRegular',
    fontWeight: 'normal',
  },
  textoNegrito: {
    fontFamily: 'MontserratBold',
    fontWeight: 'normal',
  }
});
import logo from '../../assets/logo.png';

const cesta = {
  topo: {
    titulo: "Detalhe da cesta",
  },
  detalhes: {
    nome: "Cesta de Verduras",
    logoFazenda: logo,
    nomeFazenda: "Jenny Jack Farm",
    descricao: "Uma cesta com produtos selecionados cuidadosamente da fazenda direto para sua cozinha",
    preco: "R$ 40,00",
  }
}

export default cesta;
import React from 'react';
import { StyleSheet, View } from 'react-native';

import Topo from './componentes/Topo';
import Detalhes from './componentes/Detalhes';

export default function Cesta({ topo, detalhes }) {
  return <>
    <Topo {...topo} />

    <View style={estilos.cesta}>
      <Detalhes {...detalhes} />
    </View>
  </>
}

const estilos = StyleSheet.create({
  cesta: {
    paddingVertical: 8,
    paddingHorizontal: 16,
  },
});
import React from 'react';
import { Text, StyleSheet } from 'react-native';

export default function Texto({ children, style }) {
  let estilo = estilos.texto;
  
  if(style?.fontWeight === 'bold') {
    estilo = estilos.textoNegrito;
  }

  return <Text style={[style, estilo]}>{ children }</Text>
}

const estilos = StyleSheet.create({
  texto: {
    fontFamily: 'MontserratRegular',
    fontWeight: 'normal',
  },
  textoNegrito: {
    fontFamily: 'MontserratBold',
    fontWeight: 'normal',
  }
});
import logo from '../../assets/logo.png';

const cesta = {
  topo: {
    titulo: "Detalhe da cesta",
  },
  detalhes: {
    nome: "Cesta de Verduras",
    logoFazenda: logo,
    nomeFazenda: "Jenny Jack Farm",
    descricao: "Uma cesta com produtos selecionados cuidadosamente da fazenda direto para sua cozinha",
    preco: "R$ 40,00",
  }
}

export default cesta;
import React from 'react';
import { StyleSheet, View } from 'react-native';

import Topo from './componentes/Topo';
import Detalhes from './componentes/Detalhes';

export default function Cesta({ topo, detalhes }) {
  return <>
    <Topo {...topo} />

    <View style={estilos.cesta}>
      <Detalhes {...detalhes} />
    </View>
  </>
}

const estilos = StyleSheet.create({
  cesta: {
    paddingVertical: 8,
    paddingHorizontal: 16,
  },
});
node_modules/
.expo/
dist/
npm-debug.*
*.jks
*.p8
*.p12
*.key
*.mobileprovision
*.orig.*
web-build/

# macOS
.DS_Store

# Temporary files created by Metro to check the health of the file watcher
.metro-health-check*

package-lock.json
import React from 'react';
import { StatusBar, SafeAreaView, View } from 'react-native';
import { 
  useFonts, 
  Montserrat_400Regular, 
  Montserrat_700Bold,
} from '@expo-google-fonts/montserrat';
import AppLoading from 'expo-app-loading';
import Cesta from './src/telas/Cesta';
import mock from './src/mocks/cesta';

export default function App() {
  const [fonteCarregada] = useFonts({
    "MontserratRegular": Montserrat_400Regular,
    "MontserratBold": Montserrat_700Bold,
  });

  if (!fonteCarregada) {
    return <AppLoading />
  }

  return (
    <SafeAreaView>
      <StatusBar />
      <Cesta {...mock} />
    </SafeAreaView>
  );
}
"expo": {
    "name": "react-native-comecando-do-zero",
    "slug": "react-native-comecando-do-zero",
    "version": "1.0.0",
    "orientation": "portrait",
    "icon": "./assets/icon.png",
    "userInterfaceStyle": "light",
    "splash": {
      "image": "./assets/splash.png",
      "resizeMode": "contain",
      "backgroundColor": "#ffffff"
    },
    "assetBundlePatterns": [
      "**/*"
    ],
    "ios": {
      "supportsTablet": true
    },
    "android": {
      "adaptiveIcon": {
        "foregroundImage": "./assets/adaptive-icon.png",
        "backgroundColor": "#ffffff"
      }
    },
    "web": {
      "favicon": "./assets/favicon.png"
    }
  }
}
module.exports = function(api) {
  api.cache(true);
  return {
    presets: ['babel-preset-expo'],
  };
};
"name": "react-native-comecando-do-zero",
  "version": "1.0.0",
  "main": "node_modules/expo/AppEntry.js",
  "scripts": {
    "start": "expo start",
    "android": "expo start --android",
    "ios": "expo start --ios",
    "web": "expo start --web"
  },
  "dependencies": {
    "@expo-google-fonts/montserrat": "^0.2.3",
    "expo": "~48.0.15",
    "expo-app-loading": "^2.1.1",
    "expo-font": "~11.1.1",
    "expo-status-bar": "~1.4.4",
    "react": "18.2.0",
    "react-native": "0.71.7"
  },
  "devDependencies": {
    "@babel/core": "^7.20.0"
  },
  "private": true
}
![Thumbnails GitHub](https://user-images.githubusercontent.com/9091491/123842348-0e116c80-d8e7-11eb-8618-9c15cc743335.png)

![](https://img.shields.io/github/license/nataliakt/alura-react-native-comecando-do-zero)

# ⚛️ React Native: Começando do Zero

Esse é o projeto do curso **Começando do Zero** da formação em **React Native** na [Alura](https://www.alura.com.br/).

## 📱 Projeto

Este projeto implementa a tela de detalhes da cesta do e-commerce *orgs*. Nesta tela são mostrados dados estáticos do nome da cesta, fazenda, preço e itens da cesta.

<img src="https://user-images.githubusercontent.com/9091491/123982988-e3ccb700-d999-11eb-880e-872881ee8b10.gif" width="350" />

## 🧑‍💻 Técnicas e Tecnologias

As técnicas e tecnologias utilizadas no projeto são:

- `Expo`: tecnologia para simplificar o ambiente de desenvolvimento
- `Componentes React Native`: componentes já existentes básicos da tecnologia para compor a tela
  - `Text`: componente para exibir textos
  - `View`: container para blocos de componentes
  - `ScrollView`: container para blocos de componentes com barra de rolagem
  - `Image`: componente para exibir imagens
  - `TouchableOpacity`: componente para criar áreas clicáveis
- `Componentes customizados`: criação e utilização de componentes customizados
- `Suporte a telas`: não permitir que conteúdos estejam sob a *StatusBar* (barra superior nativa) ou barra de gestos do iPhone
- `Expo Google Fonts`: suporte a fontes do google via Expo
- `StyleSheet`: estilização básica de componentes
- `Dimensions`: captura de dados das dimenções da tela

## 📲 Executando o projeto

### ✔️ Pré-requisitos

Para conseguir seguir este README e rodar o projeto você pode precisar dos seguintes itens:
- Git para clonar o projeto e acessar as branches. Você pode instalar [aqui](https://git-scm.com/downloads);
- Node para podermos rodar `expo` e `npm`. Você pode instala-lo [aqui](https://nodejs.org/en/);
- Um celular Android ou iOS com o aplicativo Expo instalado, ou então algum simulador Android ou iOS no computador;

Se quiser testar as instalações, rodar os comandos abaixo separadamente deve mostrar as respectivas versões.

```
git --version
node --version
npm --version
```

Com o `node` instalado podemos criar um projeto `expo` com o seguinte comando:
```
npx create-expo-app react-native-comecando-do-zero
```

### 🐙 Clonando o projeto

Para ter acesso aos arquivos do projeto você pode clonar usando o seguinte comando:

```
git clone https://github.com/alura-cursos/react-native-comecando-do-zero.git
```

### ▶️ Rodando o Projeto

Agora que já tem a pasta do projeto na sua máquina, dentro dela instale as dependências:
```
npm install
```

Então podemos rodar o projeto:
```
npx expo start
```

Caso estiver com o celular, **escaneie o QR code com o aplicativo do Expo** ou a câmera que aparecerá no terminal.
Se tiver um emulador, escolha o comando de execução sugerido no terminal.

Pronto, agora o app você deve ver o app rodando.
