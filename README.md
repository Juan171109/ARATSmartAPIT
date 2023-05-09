This is a replication package of ARAT-RL, which was submitted to ASE 2023.

# Set up the experiment

## Machine Specification

Our experiments were conducted on Google Cloud E2 machines, each with a 24-core CPU and 96 GB of RAM.

## Software Dependencies and Installation

If your OS is Ubuntu 20.04, you can simply run our setup script with `sh setup.sh` command in your terminal.

The following software is required for the experiment:
- Git
- Common utilities (software-properties-common, unzip, wget, gcc, git, vim, libcurl4-nss-dev, tmux, mitmproxy)
- Java 8 and 11
- Maven3
- Python 3 (with pip and virtualenv)
- Python libraries in requirements.txt
- Docker
- .NET 6 Runtime and SDK
- EvoMaster 1.6.0
- RESTler 9.1.1
- JaCoCo Agent and CLI 0.8.7

# Run the experiment

## Run tools and services

After installing all the required software, you can run the tools with this command:

```
python run.py [tool's name]
```

This command will run the tool and all the services for an hour. Possible tool names are `arat-rl`, `morest`, `evomaster-blackbox`, and `restler`. If you want to run an ablation study, you can set the tool names to: `no_prioritization`, `no_feedback`, and `no_sampling`.

## Collect the results

To collect the results, you can use this command:

```
python parse_log.py
```

It will collect the coverage and the number of responses for 2xx, 4xx, and 5xx and store the results in the `res.csv` file.