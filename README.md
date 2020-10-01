# Cashbox
Cashbox is a capital efficient market where users can deposit any ERC20 token and recieve a Pool Token which is an ownership token for your share of the pool. Users can use the cashbox to deposit a STOCK token and recieve the ERC20 at the determined rate. When buring the Pool Token for the contents of the pool token you will always recieve Stock Token as the first priority. If there isnt enought Stock Token the remaining balance will be given in the ERC20 token. There is also a Upper Cap which limits the minting of pool tokens when that upper cap is eached.

## Constructor

`constructor (address DAITokenAddr,address StockTokenAddr,uint256 daiCap,string memory name,string memory symbol,string memory url) `

1. DAITokenAddr = The address of the ERC20 token used to provide as exchange for the Stock token.
1. StockTokenAddr = The addressof the stock token
1. daiCap = The total value in ERC20 token allowed to be in the smart contract after which it 
1. name = The name of the pool token
1. symbol = Symbol of the pool token
1. url = A string to be saved in the smart contract


## CashBox Functions

 `function updateURL(string memory _url) public onlyOwner returns(string memory)`
 
 Allow the owner to update the URL string.


`function updateDAIValuationCap(uint256 daiCap) public onlyOwner returns(uint256)`

Allows the owner to update the Upper Cap of the contract.


 `function changeOwner(address payable newOwner) public onlyOwner`
 
Changes the Owner


`function updateStockTokenRate(uint256 newRate) public onlyOwner returns(uint256)`

Updates the price of the Stock token relative to the ERC20 token.


`function StockTokenAddress() public view returns (address)`

Returns the address fof the stock token.


`function _preValidateData(address beneficiary, uint256 Amount) internal pure`

Checks if wither address is a zero address or if amount is zero


 `function contractDAIBalance() public view returns(uint256 daiBalance)`
 
 Returns the balance of the ERC20 token.
 
 
 `function contractStockTokenBalance() public view returns(uint256 stockTokenBalance)`
 
  Returns the balance of the Stock Token.
 
 
` function stockTokenDAIValuation() internal view returns(uint256)`

 Returns the Value held in the contract.
 
 
 `function poolTokenTotalSupply()`
 
Returns Total Supply of Pool tokens

 
 `function getUpdatedPoolRate() internal returns (uint256 poolrate)`
 
 Returns the value of the Pool token in respect to the ERC20 token.
 
 
 `function mintPoolToken(uint256 inputDAIAmount) external`
 
 Mints pool tokens if the Upper Cap is not reached, based on the value held in the smart contract.
 
 
 `function burnPoolToken(uint256 poolTokenAmount) external`
 
 Burns the pool token as return in Stock Token and the remaining amount in ERC20 when Stock Tokens are depleted.
 
 
 
`function redeemStockToken(uint256 stockTokenAmount) external`

Trade Stock token for the ERC20 accordint to the excahnge rate.

 
 `function kill() external onlyOwner`
 
 Selfdestructs the contract
 

_All other functions used are of Open Zeppelin._
