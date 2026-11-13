# Grão Visão

Protótipo móvel para registrar a análise de qualidade de lotes de grãos. O aplicativo foi construído com Expo e React Native e oferece um fluxo de identificação do operador, seleção da cultura, coleta de leituras, decisão por limites configuráveis e relatório local.

## Estado atual

O projeto é um protótipo de interface e fluxo operacional.

- A versão Android abre a câmera e inclui um modelo TensorFlow Lite no pacote, mas a inferência no modelo ainda não foi implementada.
- O pareamento Bluetooth, a telemetria do ESP32 e a análise visual são simulados.
- A versão web usa uma animação Canvas para demonstrar a tela de inspeção; ela não acessa uma câmera nem um sensor real.
- O código exibido no relatório é apenas um identificador local. Ele não é uma assinatura criptográfica nem um registro em blockchain.

Essas limitações devem permanecer claras em qualquer demonstração, documentação comercial ou publicação do aplicativo.

## Tecnologias

- Expo SDK 54 e Expo Router
- React Native 0.81 e React 19
- TypeScript
- react-native-vision-camera
- react-native-fast-tflite

## Requisitos

- Node.js LTS
- Android Studio e um emulador ou dispositivo Android para a versão nativa

## Como executar

```bash
npm install
npx expo start
```

Para Android com módulos nativos:

```bash
npx expo run:android
```

Para a demonstração web:

```bash
npx expo start --web
```

## Verificações locais

```bash
npx tsc --noEmit
npx expo lint
```

## Estrutura

```text
app/
  _layout.tsx       Rotas do Expo Router
  index.native.tsx  Fluxo Android e câmera
  index.web.tsx     Demonstração web
assets/
  grain_model.tflite  Modelo incluído no aplicativo
android/            Projeto Android gerado pelo Expo
```

## Próximos passos para uso real

1. Implementar pré-processamento dos frames e `model.run()` para o modelo TFLite.
2. Integrar uma biblioteca BLE compatível com React Native e o protocolo real do ESP32.
3. Validar a calibração de umidade e os critérios de aprovação para cada cultura.
4. Persistir relatórios em serviço autenticado, com auditoria e criptografia quando necessário.
5. Adicionar testes unitários, de integração e em dispositivo físico.

## Licença

Defina a licença antes de publicar o repositório como público.

