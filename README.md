// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract AuctionFinalized {
    bool public finalized;

    function finalize() external {
        finalized = true;
    }
}
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract CampaignDeadline {
    uint256 public deadline;

    function setDeadline(uint256 _deadline) external {
        deadline = _deadline;
    }

    function isActive() external view returns (bool) {
        return block.timestamp < deadline;
    }
}
