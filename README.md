# Donate to Artists (Donación para Artistas)

[![](https://img.shields.io/badge/Contract-js-yellow)](https://docs.near.org/develop/contracts/anatomy)

Este contrato fue creado para la certificación Near Certified Development de Open Web Academy. El objetivo de este contrato es permitir las donaciones a cuentas específicas, pensando inicialmente para que los fanáticos donen $NEAR a artistas.

***Actualización
Se actualiza este repositorio para la certificación de BOS (Blockchain Operating System), permitiendo crear una interfaz descentralizada

## Lo que se muestra tecnicamente en este ejemplo

1. Manejo de vectores para almacenar y gestionar las donaciones realizadas por los usuarios. 
2. Uso de funciones de llamada (call) para permitir a los usuarios realizar donaciones y de consultar (view) para ver de información de las donaciones respectivamente.
3. Uso de la función near.log para registrar información útil durante la ejecución del contrato, como la cuenta del beneficiario y mensajes de agradecimiento por las donaciones.
4. Uso de la función near.promiseBatchCreate para crear un lote de promesas para transferir los fondos al beneficiario, garantizando que las transferencias se realicen de manera segura incluso si una de las funciones no se ejecuta correctamente.
5. Uso de subcomponentes en BOS, lo que permite modularidad y un mejor desarrollo de la Dapp
6. Llamada de contratos apartir de una interfaz de usuario
7. Manejo de estilos css desde un componente usando objetos

## Lo destacado en este aprendizaje como desarrollador en la Near

1. Estructura de un proyecto de contrato inteligente en NEAR, incluyendo la separación de archivos para un modelo claro y mantenible.
2. Uso de pruebas unitarias para garantizar el correcto funcionamiento del contrato y la gestión adecuada de las donaciones..
3. Despliegue exitoso de contratos inteligentes en la red de prueba de NEAR, demostrando la capacidad de llevar el contrato desde el desarrollo hasta la implementación en un entorno real.
4. Creación de interfaces de usuario descentralizadas usando BOS y React

---
### Componente web

Para ver el componente visite el siguiente enlace:  https://test.near.social/manueldesarrolla.testnet/widget/donate-to-artists.index

---
## Contrato

## Requerimientos previos
(En el caso de windows tenerlo sobre wsl)

1. Tener nodejs instalado 
2. Tener near-cli instalado
3. Tener cargo-near instalado 

# Cómo probar este contrato

Clona este repositorio de forma local 
Luego, navega desde la consola hasta la carpeta clonada y sigue estos pasos:

### 1. Instalar dependencias
Instalar las dependencias

```bash
npm install
```

### 2. Probar el contrato
Simula interacciones de usuarios automaticamente de acuerdo al archivo de pruebas unitarias ubicado en en sandbox-ts/main.ava.ts.

```bash
npm run build
```

```bash
npm run test
```

### 3. Crear una cuenta aleatoria
Cree una cuenta aleatoria donde desplegar el contrato

```bash
cargo-near near create-dev-account use-random-account-id autogenerate-new-keypair save-to-legacy-keychain network-config testnet create
```


### 4. Desplegar el contrato en la cuenta creada
Despliega tu contrato en un entorno de prueba 

```bash
near deploy <id-account-created> build/donate_to_artists.wasm 
```

### 5. Realizar donación

Llame el contrato desde la cuenta creada y el la cuenta beneficiaria cambiela por una de prueba

```bash
near call <id-account-created> donate '{"beneficiary": "<account-beneficary-id>"}' --amount 1 --accountId <id-account-created>
```
### 6. Revise las donaciones echas
Con el siguiente comando podrá ver las donaciones echas

```bash
near view <id-account-created> get_donations
---
