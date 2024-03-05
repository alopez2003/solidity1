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

Vemos que se estableció el valor "owner" de la información de lectura del contrato con el valor establecido desde un inicio en el smart contract

![image](https://github.com/alopez2003/solidity1/assets/67942268/94839ca5-c559-4b32-9b45-e8ed3c43eedb)

### Añadir un dato al Smart Contract

Posteriormente conectamos en el Contrato en el Etherscan de Goerli a Metamask, y vemos ligada nuestra dirección, y damos click en "Write Contract", damos click en "register" y damos un valor, en este caso "PruebaGoerliALG" y posteriormente en Write

![image](https://github.com/alopez2003/solidity1/assets/67942268/eac5bbcc-2d67-4d66-80c9-62c8eabfa9dd)

Nos sale una ventana de Metamask para confirmar la transacción

![image](https://github.com/alopez2003/solidity1/assets/67942268/9270bf23-425f-4fe4-a60e-0d5c7a19bbaa)

Damos click en Confirmar y podemos ver un boton al lado de Write que nos dice "View your transaction"

![image](https://github.com/alopez2003/solidity1/assets/67942268/d10b9f27-f82f-47c1-a21f-178968ad37de)

Si damos click al boton, nos llevará a la siguiente liga, que es la verificación de que se ejecutó esa función.

https://goerli.etherscan.io/tx/0x77c39cce79a39052f8015acecdcc5ee80e45ec0512539c63e507a5de72b5ed26

Misma que podemos ver reflejada en el contrato

![image](https://github.com/alopez2003/solidity1/assets/67942268/3362694f-9b1a-4189-9793-67a93fa1fbcd)

### Leer un dato del Smart Contract

Así mismo si damos click en la parte de "Read Contract" y expandemos la parte de "getHashEvidence" y escribimos "PruebaGoerliALG" nos dará el timestamp asignado a la transacción.

![image](https://github.com/alopez2003/solidity1/assets/67942268/664a8c7a-f860-4032-887d-cad4dd3cd2f4)

Esto si lo vemos en epochconverter.com podremos ver que es reciente su creación.

![image](https://github.com/alopez2003/solidity1/assets/67942268/df796658-cf3a-41e3-ab14-8aeed2f98365)

Si cambiamos ahora de la red de Goerli a la de Polygon Mumbai, con la misma dirección con la que se hizo el deploy, y ejecutamos la función de "Register" con un valor "PruebaPolygonALG" sucede lo siguiente:

![image](https://github.com/alopez2003/solidity1/assets/67942268/b29fa518-5117-4af0-8dc7-cd073137863d)

![image](https://github.com/alopez2003/solidity1/assets/67942268/bef94bc4-ccde-47ab-b436-313aef132628)

No nos deja hacer el cambio puesto que estamos en una red diferente.

Ahora, dentro de la red de Goerli nuevamente, cambiamos de cuenta (Account2), que tiene una dirección "0x80392D2071c4E1aBBDdD3DBf8eaCa4431081b787" y hacemos la prueba con el "Register" ahora con un valor "PruebaGoerliALG3", cambiando previamente la dirección dentro de Goerli Etherscan.

![image](https://github.com/alopez2003/solidity1/assets/67942268/4c6b5fd5-329e-4b0e-88cb-d06b395fe614)

Nos dice que hay un error en el contrato y el Gas Fee nos lo establece muy alto, por lo que no podemos ejecutar la transacción.

### Editar un dato del Smart Contract

Cambiamos nuevamente hacia el Account1, donde tenemos el owner, y establecemos un nuevo dueño con la función de "setOwner" hacia el Account2

![image](https://github.com/alopez2003/solidity1/assets/67942268/bca62e83-5530-468d-96aa-0f3d3cf8e651)

Pide confirmar la transacción en MetaMask

![image](https://github.com/alopez2003/solidity1/assets/67942268/a1b24f64-3475-4b16-91c5-872bae16e6d7)

Y podemos ver que el owner ha sido actualizado

![image](https://github.com/alopez2003/solidity1/assets/67942268/1cc95a1e-9cbe-4f66-a022-334e08a4618e)

Así mismo, podemos ver en el contrato que ha sido actualizado el contrato con la función "Set Owner"

![image](https://github.com/alopez2003/solidity1/assets/67942268/cc110e7c-eee4-49f5-8b0e-dccf727324b4)

Ahora si volvemos a intentar hacer el Write en la función "Register" con el valor "PruebaGoerliALG4", cambiando previamente la cuenta en MetaMask y actualizando la dirección dentro de Goerli Etherscan

![image](https://github.com/alopez2003/solidity1/assets/67942268/def0e8ba-ab5f-4bd4-b698-db889ddf9c97)

Pide confirmación

![image](https://github.com/alopez2003/solidity1/assets/67942268/390f3d93-2b17-4b1d-9276-bd07f798a9e9)

Y podemos ver la transacción, ahora con el nuevo owner

https://goerli.etherscan.io/tx/0x8a69fa769d0ab2c0fb78da269b629825006824a66c2700de880b1887c12eb916
.
Esto podemos comprobarlo en la URL del contrato, donde se puede ver que el From ya es diferente (nuevo owner)
Se anexa nuevamente la liga del contrato
https://goerli.etherscan.io/address/0x51cb8f44e5644a0e62ee33d26fc7939f7d30d934


![image](https://github.com/alopez2003/solidity1/assets/67942268/d098125f-eccb-4346-9b12-2644c901041f)

Viendo ahora la red de Polygon Mumbai, podemos ver que se desplegó el contrato inteligente, en otra red, siendo otro contrato diferente.

https://mumbai.polygonscan.com/address/0xb62806e9Ae935d616C983374FfC91903C719a5D1

Se añade la URL del contrato

https://mumbai.polygonscan.com/address/0x51cb8f44e5644a0e62ee33d26fc7939f7d30d934

De la misma forma podemos ver que el owner es la direccion 0xb62806e9Ae935d616C983374FfC91903C719a5D1

![image](https://github.com/alopez2003/solidity1/assets/67942268/5d8bffc5-d702-42d2-bd20-4e3dcd183697)

### Añadir un dato a otro Smart Contract

Si escribimos en el apartado de Write en la función de Register "PruebaPolyALG1"

![image](https://github.com/alopez2003/solidity1/assets/67942268/3a963906-9e63-472c-b98d-2bb9dad288cc)

Nos pide confirmar

![image](https://github.com/alopez2003/solidity1/assets/67942268/3dd2ef19-4141-48aa-9c08-c579ec923005)

Podemos verificar la transacción en la siguiente liga:

https://mumbai.polygonscan.com/tx/0x2008f04123d8d33f5139a70b557980d88e3d85066117119b16da57cae82f3470

Así mismo vemos que queda registrado en el URL del contrato

![image](https://github.com/alopez2003/solidity1/assets/67942268/d520d104-9511-4488-ac4f-a1f9b590eb71)

### Editar un dato de otro Smart Contract

Hacemos una reescritura del owner hacia el Account2 con dirección 0x80392D2071c4E1aBBDdD3DBf8eaCa4431081b787 y damos click en Write

![image](https://github.com/alopez2003/solidity1/assets/67942268/19082080-06a8-478f-9768-b9bc7b8fe7a4)

Nos pide confirmación

![image](https://github.com/alopez2003/solidity1/assets/67942268/0ce8fa87-aa4d-49ed-a7fd-cf1c6b593308)

Y vemos la confirmación en la siguiente URL

https://mumbai.polygonscan.com/tx/0xaecf7dbe5f0f132dc17f9b1e3dde8bf79296ba982012535c8769cbb93e020757

Con esto invocamos un Write en la funcion "Register" ahora con el Account2

![image](https://github.com/alopez2003/solidity1/assets/67942268/97c850b4-5f59-468b-ad74-cc90d7430bb2)

Nos pide confirmar

![image](https://github.com/alopez2003/solidity1/assets/67942268/59a1cc78-fb5c-48fd-9adc-94eb403f94ee)

Y queda registrado en la siguiente liga:

https://mumbai.polygonscan.com/tx/0xbd08b887eb294891306a47573bff57162f34002fc6faf8ef5230a2ec3fa8820d

### Leer un dato de otro Smart Contract

Ahora hacemos la consulta en Polygon Mumbai de lo establecido en la función Register desde la parte Read y nos devuelve el timestamp

![image](https://github.com/alopez2003/solidity1/assets/67942268/000b4efa-466c-4577-bca6-3662f072f804)

Buscamos este valor en epochconverter.com y podemos ver que fue creado hace unos momentos

![image](https://github.com/alopez2003/solidity1/assets/67942268/5c02cb8d-bbe6-4fff-baff-0ec579cc9c34)

Agrego nuevamente la dirección del contrato para constatar las operaciones realizadas

https://mumbai.polygonscan.com/address/0x51cb8f44e5644a0e62ee33d26fc7939f7d30d934

Con esto dimos respuesta a lo siguiente:

       - Añadir un dato al Smart Contract (realizado en Goerli)

       - Añadir un dato a otro Smart Contract (realizado en Polygon Mumbai)

       - Leer un dato del Smart Contract (realizado en Goerli)

       - Leer un dato de otro Smart Contract (realizado en Polygon Mumbai)

       - Editar un dato del Smart Contract (realizado en Goerli)

       - Editar un dato de otro Smart Contract (realizado en Polygon Mumbai)

En específico aún no añadimos funciones nuevas, se estarán investigando dichas funciones.

Se anexa el código de Notarization.sol, que fue el mismo que se ocupó para este ejercicio.
