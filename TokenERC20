contract TokenERC20 {
    string public name;
    string public symbol;
    uint8 public decimals = 18;
    uint256 public totalsupply; //Cantidad maxima de tokens en este contrato
    mapping (address => uint256) public balanceOf;
    
    event Transfer(address from, address tom, uint256 value);
    
    constructor(uint256 initialSupply, string memory tokenName, string memory tokenSymbol) public {
        totalsupply = initialSupply * 10** uint256(decimals);
        name = tokenName;
        symbol = tokenSymbol;
        balanceOf[msg.sender] = totalsupply;
    }
    
    function _transfer(address _from, address _to, uint _value) internal{
        require(balanceOf[_from]>=_value);
        require(balanceOf[_to]+_value> balanceOf[_to]);
        uint previousBalance = balanceOf[_from] + balanceOf[_to];
        balanceOf[_from] -= _value;
        balanceOf[_to] += _value;
        
        emit Transfer(_from,_to,_value);
        assert(balanceOf[_from] + balanceOf[_to] == previousBalance);
    }
    
    function transfer(address _to, uint256 _value) public {
        _transfer(msg.sender,_to,_value);
    }
}

interface TokenERC20Interface {
    function transfer(address _to, uint256 _value) external;
}

contract BasicContract{
    function transferToken() public{
            TokenERC20Interface token = TokenERC20Interface(0xCA35b7d915458EF540aDe6068dFe2F44E8fa733c);
            token.transfer(0x583031D1113aD414F02576BD6afaBfb302140225,1);
    }
}
