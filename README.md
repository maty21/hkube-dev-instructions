# hkube-dev-instructions


## pre install

 - for running on windows we have to install wsl2 
 - install ubuntu wsl from the store https://docs.microsoft.com/en-us/windows/wsl/install-win10
 - config docker to run with wsl2 configuration https://docs.docker.com/desktop/windows/wsl/
 - install windows terminal from the store 
 - install nvm https://www.liquidweb.com/kb/how-to-install-nvm-node-version-manager-for-node-js-on-ubuntu-12-04-lts/
 - install dependencies for msgpack  `sudo apt-get install gcc` and `sudo apt-get install build-essential`
 - install `zsh` https://blog.nillsf.com/index.php/2020/02/17/setting-up-wsl2-windows-terminal-and-oh-my-zsh/
 - install venv `python3 -m venv /path/to/new/virtual/environment`
 - create venv folder `~/dev/venv`
 - set venv enviroment `source ~/dev/venv`
 - install wheel `pip install wheel`
 - install python3 dev `sudo apt install python3-dev`
 - install hkube's wrapper `pip install hkube-python-wrapper` 

## install hkube
 - create `dev` folder
 - clone hkube `git clone https://github.com/kube-HPC/hkube.git`
 - clone monitor server `git clone https://github.com/kube-HPC/monitor-server.git`
 - clone dashboard `git clone https://github.com/kube-HPC/simulator.git`
 - install lerna in global `npm i -g lerna` 
 - run  `lerna bootstrap` from `~/dev/hkube`
 - run `npm install` to the monitor-server and the simulator 
 - clone this repo 
 - create folder `~/.kube/` and copy the `config file` from this repo to the flolder 
 - create folder `~/dev/algorithms` and copy `alg1.py` from this repo to the flolder 
 - copy the `dockers` folder to `~/dev/~`

## running hkunbe
 - run dockers `cd ~/dev` then run `hkube-docker.sh`
 - api-server `cd ~/dev/hkube/core/api-server` run  `npm start`
 - pipeline driver `cd ~/dev/hkube/core/pipeline-driver` run  `npm start`
 - pipeline driver queue `cd ~/dev/hkube/core/pipeline-driver-queue` run  `npm start`
 - algorithm operator `cd ~/dev/hkube/core/algorithm-operator` run  `DEV_MODE=true npm start`
 - algoritm-queue `cd ~/dev/hkube/core/algorithm-queue` run  `QUEUE_ID="foo-bar-zuzu"  npm start`
 - worker   `cd ~/dev/hkube/core/worker` run  ` ./runWithRandoPort.sh "green-alg" "python3 /home/{userName}/dev/alg1.py"` 
 - monitor server `cd ~/dev/hkube/monitor-server` run  `npm start`(in windows for wsl since wslhost use port 5000) run `HEALTHCHECK_PORT=5002 npm start`
 - dashboard `cd ~/dev/hkube/simulator` run  `npm start`




