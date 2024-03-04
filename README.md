# Programación de un primer Smart Contract por Alberto López Gutiérrez

Este es mi primer proyecto en Solitidy y tiene mucho tiempo que no programo, así que estoy muy emocionado por esto. Comencemos.

NOTA: Desde que inicié este master, no ha existido un grupo, siempre hemos entregado mis compañeros y yo el trabajo de forma individual, me parece que sólo ha habido un grupo. En mi caso continuaré con la entrega individual. Muchas gracias!!

## Sprint 1

Lo siguiente fue desplegado en un Ubuntu LTS 22.04, lo primero que hice fue instalar Node.js en el ubuntu, recurrí directamente a las herramientas de Ubuntu (APT) donde instale nodejs y también npm, se puede verificar su versión. Ocupé el blog de [Edward S. & Aris B.](https://www.hostinger.com/tutorials/how-to-install-node-ubuntu?ppc_campaign=google_search_generic_hosting_all&bidkw=defaultkeyword&lo=9047091&gad_source=1&gclid=CjwKCAiAuYuvBhApEiwAzq_Yiay1MIqRX_uv-ElLgxUZHYyhim5ske-hRuoeqoNvAhFRWnORk975dhoCFjUQAvD_BwE) de Hostinger para realizar esta operación.

![image](https://github.com/alopez2003/solidity1/assets/67942268/e2516ef8-bb1d-4567-a0ec-0fd30325750b)

Posteriormente instalamos Hardhat conforme al Github de [Alex Herranz](https://github.com/Alexander-Herranz/smart-contract-deployment-public-networks/blob/main/README.md)

![image](https://github.com/alopez2003/solidity1/assets/67942268/cb6f00ec-785f-403e-bef5-1214a6490750)

![image](https://github.com/alopez2003/solidity1/assets/67942268/7904da7f-7def-45c4-a79a-fbb60b87d5dd)

Tuvimos que actualizar node.js y npm porque Hardhat no encontró compatibilidad con la versión instalada por Ubuntu, me apoyé del artículo de [Karim Budzar de Linux Genie](https://linuxgenie.net/how-can-i-update-my-nodejs-to-the-latest-version-on-ubuntu/)

![image](https://github.com/alopez2003/solidity1/assets/67942268/b3cbf0bc-acaa-4990-b63d-525ad86917c1)

Instalamos Hardhat

![image](https://github.com/alopez2003/solidity1/assets/67942268/d3cba2c1-70ea-4eec-bcfd-e3164a0ce9ec)


Se hace la compilación y el clean del código desplegado

![image](https://github.com/alopez2003/solidity1/assets/67942268/26545488-80a3-4a3c-bcac-37715797d564)

Al momento de ejecutar el código nos marcó un error de fondos insuficientes, conseguimos fondos para la cuenta 1 con Address: 0xb62806e9Ae935d616C983374FfC91903C719a5D1

Una vez que tenemos saldo en la cuenta, procedemos con la ejecución.

![image](https://github.com/alopez2003/solidity1/assets/67942268/2d6883d8-afed-4a19-a8a3-c024ca8622e7)

![image](https://github.com/alopez2003/solidity1/assets/67942268/213c4ffb-22b0-468d-a57a-48ed9e3c3450)

_Nota: Usualmente los comandos los despliego en un SSH conectado al Ubuntu, sin embargo cada vez que lo intentaba desplegar me marcaba un ConnectionTimeout_


Podemos verificar la creación del contrato en la cuenta en Etherscan en la siguiente liga:

https://goerli.etherscan.io/tx/0x6f9f9511fc8d5180796125ac5524bde29d4be3a1f4bd1980add7720d6d5fa425

Hacemos el deploy también en la red de Polygon en la testnet de Mumbai

![image](https://github.com/alopez2003/solidity1/assets/67942268/f1f1f5a5-c10e-4e1e-a378-e817f397c3d6)


Podemos verificar la creación del contrato en la cuenta de Polyscan en la siguiente liga:

https://mumbai.polygonscan.com/tx/0x25580b3df84079924d12baafa9e9069c6d4f874aad9d5229c87f9925403699c9

Estuve intentando verificar a través del comando verify, sin embargo me marcaba un error.

![image](https://github.com/alopez2003/solidity1/assets/67942268/9a9990e1-bf16-47d0-bdb8-42905903b315)

Considerando que tanto en etherscan y en polyscan puedo ver los contratos, seguiré adelante.





