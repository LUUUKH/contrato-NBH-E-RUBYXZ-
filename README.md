# contrato-NBH-&-RUBYXZ-
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
    
    function obterProprietarioMajoritario() public view returns (string memory) {
        return "Lucas Januário do Nascimento";
    }
}
```

Agora, o contrato inclui uma função `obterProprietarioMajoritario()` que retorna o seu nome, Lucas Januário do Nascimento, como o proprietário majoritário.
