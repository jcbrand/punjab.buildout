# punjab.buildout

A [zc.buildout](https://pypi.python.org/pypi/zc.buildout/2.5.1) configuration for the [Punjab](https://github.com/twonds/punjab) BOSH server.

It installs the [supervisor](http://supervisord.org/) process manager to ensure that Punjab stays up.

It uses [mr.developer](https://pypi.python.org/pypi/mr.developer) to check out Punjab, it will be checked out to `./src/punjab`.

## Installation

### Dependencies

Make sure you have the FFI development libraries installed, on Ubuntu/Debian you can run the following:

    sudo apt-get install libffi-dev gcc python-virtualenv python-dev libssl-dev

### Running buildout

    git clone https://github.com/jcbrand/punjab.buildout.git
    python3 -m venv punjab.buildout
    cd punjab.buildout
    source bin/activate
    ./bin/pip install -r requirements.txt
    ./bin/buildout -v

### Starting Punjab

    ./bin/supervisord

### Tailing the logs

    sudo apt-get install multitail
    
    multitail -f ./var/log/*.log
