# RamiGPT

**RamiGPT** is an AI-powered offensive security agent designed to pwn root accounts. Leveraging [PwnTools](http://github.com/Gallopsled/pwntools) and OpwnAI capabilities, RamiGPT navigated the privilege escalation scenarios of several systems from [VulnHub](https://www.vulnhub.com/), getting root access in less than a minute.


## Timing Table

| Task Description | Source | Start Time | End Time | Elapsed Time in Seconds | Model |
|------------------|------------|------------|----------|--------------|-------|
| symfonos5 | https://www.vulnhub.com/entry/symfonos-52,415/ | 2025-11-28 20:18:28.367 | 2025-11-28 20:19:18.888 | 0:00:50.521 | gpt-5-mini |
| Escalate Linux 1 | https://www.vulnhub.com/entry/escalate_linux-1,323/ | 01.306601 | 14.134318 | 12.827717 | gpt-3.5-turbo |
| Nyx 1 | https://www.vulnhub.com/entry/nyx-1,535/ | 55.620576 | 05.664968 | 10.044392 | gpt-3.5-turbo |
| Venom: 1 | https://www.vulnhub.com/entry/venom-1,701/ | 25.598964 | 35.268614 | 09.669650 | gpt-3.5-turbo |
| digitalworld.local: TORMENT | https://www.vulnhub.com/entry/digitalworldlocal-torment,299/ | 50.893860 | 00.622965 | 09.729105 | gpt-3.5-turbo |
| digitalworld.local: DEVELOPMENT | https://www.vulnhub.com/entry/digitalworldlocal-development,280/ | 47.539752 | 57.450881 | 09.911129 | gpt-3.5-turbo |
| Tiki: 1 | https://www.vulnhub.com/entry/tiki-1,525/ | 44.877072 | 55.043536 | 10.166464 | gpt-3.5-turbo |
| hacksudo: L.P.E. | https://www.vulnhub.com/entry/hacksudo-lpe,698/ | 12.234327 | 22.080433 | 09.846106 | gpt-3.5-turbo |
| DC: 2 | https://www.vulnhub.com/entry/dc-2,311/ | 16.866599 | 26.526931 | 09.660332 | gpt-3.5-turbo |
| DevGuru: 1 | https://www.vulnhub.com/entry/devguru-1,620/ | 43.240171 | 53.594361 | 10.354190 | gpt-3.5-turbo |
| serial: 1 | https://www.vulnhub.com/entry/serial-1,349/ | 23.184360 | 32.802188 | 09.617828 | gpt-3.5-turbo |
| Dina: 1.0.1 | https://www.vulnhub.com/entry/dina-101,200/ | 22.744572 | 32.429961 | 09.685389 | gpt-3.5-turbo |
| Autonomous - Hostname:pehost, Server:None, Username:zeus | Link | 2025-11-28 19:46:57.241595 | 2025-11-28 19:47:07.604764 | 0:00:10.363169 | gpt-3.5-turbo |
| Autonomous - Hostname:pehost, Server:None, Username:zeus | Link | 2025-11-28 20:07:27.607245 | 2025-11-28 20:07:37.551688 | 0:00:09.944443 | gpt-3.5-turbo |

---

## GUI:

>![alt text](screenshots/poc_pwn.gif)


## Configuration: Setting Up Your OpenAI API Key

To use RamiGPT's capabilities, you'll need an OpenAI API key. Follow these steps to obtain and configure your key:

### Obtaining an OpenAI API Key

1. **Create an Account:** Visit [OpenAI](https://www.openai.com/) and sign up for an account if you don't already have one.
2. **Apply for API Access:** Navigate to the API section and apply for access. You might need to provide details about your intended use case.
3. **Get Your API Key:** Once approved, you will receive an API key. 

### Configuring the API Key in Your Environment

1. **Copy the `.env.example` File:** In the root directory of the RamiGPT project, copy the file `.env.example` and name it `.env`.
   ```
   cp .env.example .env
   ```
2. **Add Your API Key:** Open the `.env` file and add the following line:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```
   Replace `your_api_key_here` with the API key you obtained from OpenAI.

## Run with Docker

### Prerequisites

Before running the project, ensure you have installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- OpenAI key

### Setup

Clone the repository and launch the Docker containers:

```sh
git clone https://github.com/M507/RamiGPT.git
cd RamiGPT
docker compose up -d
```

Access the application at: [https://127.0.0.1:5001](https://127.0.0.1:5001)

## Run Locally

### Prerequisites

Ensure the following are installed:

- Python 3 and pip
- OpenAI key

### Setup

Clone the repository and prepare the environment:

```sh
chmod +x ./generate_certs.sh
./generate_certs.sh
pip3 install -r requirements.txt
python3 app.py
```

Access the application at: [https://127.0.0.1:5000](https://127.0.0.1:5000)

## Integrated Tools

RamiGPT integrates several tools for privilege escalation enumeration, including:

- **[BeRoot](https://github.com/AlessandroZ/BeRoot)**: A tool for identifying common privilege escalation vectors in Windows environments.
- **[LinPEAS](https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS)**: A script that audits Linux environments for potential misconfigurations and vulnerabilities.

These tools are automatically employed or recommended by RamiGPT depending on the target environment.


## Features

### Import and export instructions

For example, to capture a flag:
>![alt text](screenshots/poc_flag.gif)

### Use external tools for enumerations

For example, executing BeRoot and feeding the results to the AI:
>![alt text](screenshots/proof_of_concept_beroot.gif)


## Disclaimer

RamiGPT is intended solely for **educational and authorized security testing**. Use it responsibly and only on systems where you have explicit permission to conduct tests.

