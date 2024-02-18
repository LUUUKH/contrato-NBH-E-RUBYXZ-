# contrato-NBH-&-RUBYXZ-
Claro, aqui está um contrato básico em Solidity para estabelecer os direitos autorais sobre uma tecnologia em nome de Lucas Januário do Nascimento:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract DireitosAutorais {
    address public proprietario;
    string public tecnologia;
    
    event TransferenciaPropriedade(address proprietarioAntigo, address novoProprietario);

    constructor(string memory _tecnologia) {
        proprietario = msg.sender;
        tecnologia = _tecnologia;
    }

    modifier apenasProprietario() {
        require(msg.sender == proprietario, "Apenas o proprietário pode executar esta ação.");
        _;
    }

    function transferirPropriedade(address novoProprietario) public apenasProprietario {
        require(novoProprietario != address(0), "Endereço do novo proprietário inválido.");

        proprietario = novoProprietario;

        emit TransferenciaPropriedade(msg.sender, novoProprietario);
    }
    
    function obterProprietario() public view returns (address) {
        return proprietario;
    }

    function obterTecnologia() public view returns (string memory) {
        return tecnologia;
    }
}
```

Este contrato permite a Lucas Januário do Nascimento registrar sua propriedade sobre uma tecnologia específica na blockchain Ethereum. Ele pode inicializar o contrato com o nome da tecnologia e, em seguida, transferir a propriedade para outros endereços, se necessário. O contrato registra o endereço do proprietário atual e fornece métodos para acessar informações sobre a tecnologia e o proprietário.
