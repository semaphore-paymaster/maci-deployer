maci-deployer
-------------

GitHub Actions workflow to deploy MACI.

This repository uses the Hardhat tasks in [`maci-contracts`](https://github.com/privacy-scaling-explorations/maci/tree/dev/contracts) to deploy MACI. Configurations in `config/` directory and the GitHub actions workflow in this repository is tailored to deploy in Sepolia network.

## Deploy MACI

### Pre-requisite

Make sure you deployed Semaphore contract and created Semaphore group 

### Deploy

1. Change following values in `configs/deploy-config.json` to set Semaphore gatekeeper:

* SemaphoreGatekeeper.semaphoreContract
* SemaphoreGatekeeper.groupId

2. Commit change and push the change

3. GitHub Actions will be triggered and deployment will performed

4. You can check the addresses of deployed contract in CI log. (See https://github.com/semaphore-paymaster/maci-deployer/actions/runs/9806497037/job/27078340120#step:9:204 for example)

### GitHub Secrets

make sure you set following GitHub Actions secret :
 * `ETH_SK`: Private key of your Ethereum account
 * `SEPOLIA_RPC_URL`: RPC provider
 * `ETH_ETHERSCAN_API_KEY`: Etherscan API key to verify contract



maci-deployer
-------------

This repository manages GitHub Actions workflow to deploy MACI with Semaphore gatekeeper into Sepolia network. It uses the Hardhat tasks from [`maci-contracts`](https://github.com/privacy-scaling-explorations/maci/tree/dev/contracts).

## Deploy MACI

### Prerequisites

- **Semaphore Contract**: Semaphore contract is deployed
- **Semaphore Group**: Semaphore group is created

### Deployment Steps

1. **Update Configuration**:
   Modify the following parameters in `configs/deploy-config.json` to configure your Semaphore gatekeeper:
   - `SemaphoreGatekeeper.semaphoreContract`: Address of the Semaphore contract
   - `SemaphoreGatekeeper.groupId`: ID of the Semaphore group

2. **Commit and Push**:
   Commit your change and then push them to your repository to trigger the GitHub Actions deployment workflow

3. **Check Deployment**:
   Access the CI logs to verify the addresses of the deployed contracts. For an example of what to look for, see [this job log](https://github.com/semaphore-paymaster/maci-deployer/actions/runs/9806497037/job/27078340120#step:9:204).

### GitHub Secrets

Configure the following secrets within GitHub Actions:

- `ETH_SK`: The private key of your Ethereum account
- `SEPOLIA_RPC_URL`: The RPC provider for Sepolia network
- `ETH_ETHERSCAN_API_KEY`: An Etherscan API key for contract verification
