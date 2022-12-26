cd contarcts/token
configure locklift.config.* like in step 3.
do npm install
fix error from step 4



1. cd contarcts/bridge/everscale
2. Copy and replace locklift.config.js with my verison from repo configs directory.
3. Open and configure ***locklift.config.js***

Set path to your solc(Solidity compiler) and TVM_Linker
Note, that you need 0.57.3 compiler version and 
The best way to install them is everdev
Install it with:
> npm install everdev
And solc and linker now.
> npx everdev sol set --compiler 0.57.3 --linker 0.14.36
They are installed to /home/$HOME/.everdev/solidity/
Set path to them in ***locklift.config.js***

Also you need giver contarct, you can use mine from my config. Or you can deploy it by yourself with tonos-cli.
If you used my giver exec this in shell.
> export DEV_GIVER_KEY=14dcf8b8acf3e495d42214e9ca2d0bd43511fda4f83818e67a1480a0f9e5974b

4. Fix dependency

Open ../node_modules/locklift/locklift/cli/utils.js

And add "**--lib ~/.everdev/solidity/stdlib_sol.tvm**" after compile word in this line.
> const tvmLinkerLog = execSync(`cd ${this.options.build} && ${this.config.linker.path} compile "${contractNameNoFolderStructure}.code" -a "${contractNameNoFolderStructure}.abi.json"`);

5. Build contarcts

> npx locklift build --config ./locklift.config.js
