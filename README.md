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
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract PendingRewards {
    mapping(address => uint256) public pending;

    function addReward(uint256 amount) external {
        pending[msg.sender] += amount;
    }
}
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract EmergencyWithdraw {
    bool public emergency;

    function enableEmergency() external {
        emergency = true;
    }
}
