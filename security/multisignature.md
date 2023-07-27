---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Multisignature

Cascadia assets are secured by [Safe](https://safe.cascadia.foundation/welcome).  Safe is a popular and versatile multisignature wallet that provides advanced transaction capabilities and secure storage for digital assets.  It meets best practice industry security standards (Formal Verification) and requires a predefined number of users to approve transactions.  This prevents unauthorized access and unnecessary losses.  Additionally, Safe allows for decentralized gasless voting, which makes governance more inclusive.  The Cascadia Safe has been customized to meet the specific needs of the Cascadia network.



**Deployed services include:**

* [safe-client-gateway](https://github.com/CascadiaFoundation/safe-client-gateway), which provides backend services for clients, such as transaction services and nodes;
* [safe-config-service](https://github.com/CascadiaFoundation/safe-config-service), which provides configuration information in the context of the Safe client environment;
* [safe-transaction-service](https://github.com/CascadiaFoundation/safe-transaction-service), which tracks Safe contract transactions; and
* [safe-wallet-web](https://github.com/CascadiaFoundation/safe-wallet-web), which enables user asset management.



**Multisignature Wallets (Cascadia)**

<table data-header-hidden><thead><tr><th width="283"></th><th></th></tr></thead><tbody><tr><td>Fee Distributor</td><td>0x7F6a184734cedD31b52cffE601ce614F2a218D5A</td></tr><tr><td>nProtocol</td><td>0x3abc14Aeab2e37134A8215Aca1A9272833a3047b</td></tr><tr><td>Treasury</td><td>0xa3fE3DfdfF52eD79850623665106eBB1B0749029</td></tr></tbody></table>



**Multisignature Wallets (Ethereum)**

<table data-header-hidden><thead><tr><th width="284"></th><th></th></tr></thead><tbody><tr><td>Escrow</td><td>0xA83fa8f1A7Ff19DFe6d7377Cfb3dAf24d5B4804E</td></tr></tbody></table>



**Contracts**

<table data-header-hidden><thead><tr><th width="288">Description</th><th>Contract Address</th></tr></thead><tbody><tr><td>SimulateTxAccessor</td><td>0x3b8F8591a3a8143b98F2a684F64cFACD1529AfB9</td></tr><tr><td>SafeProxyFactory</td><td>0x9de305bBC84C1A25CF750569F99b4D91e369D7F5</td></tr><tr><td>TokenCallbackHandler</td><td>0x26788816c7Ed36FB9a7D391dc5bac3D2256f7327</td></tr><tr><td>CompatibilityFallbackHandler</td><td>0xC529Ffba7ca6D474cB58bC37E94927AE90d00efE</td></tr><tr><td>CreateCall</td><td>0xA0b575f0bDc9E12e5CAEBc962C59e49C819B6F26</td></tr><tr><td>MultiSend</td><td>0x0864ADD7052055E97d33Eff28aA3Aa689Fe9fd01</td></tr><tr><td>MultiSendCallOnly</td><td>0xe04249805C956Ea1928Ab6798D12b85faCE8407c</td></tr><tr><td>SignMessageLib</td><td>0x779b9af59c3479f838050c2eE4975a6a96C1637C</td></tr><tr><td>SafeL2</td><td>0x0D179CE98e0122D265805Cf5848dfB9D79ed285d</td></tr><tr><td>Safe</td><td>0x0CF9477f3683A20C801705DCA97cB5EDc49A44E3</td></tr></tbody></table>
