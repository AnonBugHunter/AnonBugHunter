-
<!---
AnonBugHunter/AnonBugHunter is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
This post contains results i got from scanning NEST PROTOCOL ethereum contract address 0x04abeda201850ac0124161f037efd70c74ddc74c from Smartbugs github Repository. 


SmartBugs is an execution framework aiming at simplifying the execution of analysis tools on datasets of smart contracts.

Features
A plugin system to easily add new analysis tools, based on Docker images;

Parallel execution of the tools to speed up the execution time;

An output mechanism that normalizes the way the tools are outputting the results, and simplifies the process of the output across tools.

Automatic detection and download of the correct version of the Solidity compiler as required by the contract under analysis.

Supported Tools
HoneyBadger
Maian
Manticore
Mythril
Osiris
Oyente
Securify
Slither
Smartcheck
Solhint
Conkas
Requirements
Unix-based system
Docker
Python3
Installation
Once you have Docker and Python3 installed your system, follow the steps:

Clone SmartBugs's repository:
git clone https://github.com/smartbugs/smartbugs.git
Install all the Python requirements:
pip3 install -r requirements.txt
Usage
SmartBugs provides a command-line interface that can be used as follows:

smartBugs.py [-h, --help]
              --list tools          # list all the tools available
              --list datasets       # list all the datasets available
              --dataset DATASET     # the name of the dataset to analyze (e.g. reentrancy)
              --file FILES          # the paths to the folder(s) or the Solidity contract(s) to analyze
              --tool TOOLS          # the list of tools to use for the analysis (all to use all of them) 
              --info TOOL           # show information about tool
              --skip-existing       # skip the execution that already has results
              --processes PROCESSES # the number of process to use during the analysis (by default 1)
              --output-version      # specifies SmartBugs' output version {v1 (Json), v2 (SARIF), all}
              --aggregate-sarif     # aggregates SARIF output per analysed file
              --unique-sarif-output # aggregates all analysis in a single file
              --import-path PATH    # defines project's root directory so that analysis tools are able to import from other files
For example, we can analyse all contracts labelled with type reentrancy with the tool oyente by executing:

python3 smartBugs.py --tool oyente --dataset reentrancy
To analyze a specific file (or folder), we can use the option --file. For example, to run all the tools on the file dataset/nest.sol, we can run:
