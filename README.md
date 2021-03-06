# docs-seed repo
Contains the documentation site implementation.

- [Local Setup :computer:](#local-setup)

## Local Setup
This section describes the best practices about what and how should be done in order to run the documentation locally.

### Prerequisites
- Install Docker (Community Edititon(CE) is enough) - please use the [official Docker installation](https://docs.docker.com/install/) guide. Accept the default installation instructions (use Linux containers, etc.)    
  - From the Docker Settings window, share the drive where the documentation repos reside with Docker.
- Pull the repo to which you want to contribute (we will refer to that repo later as 'MY-REPO')

### Instructions
- Clone the current repo 
```bash
git clone git@github.com:telerik/docs-seed.git
```

- Go to the directory in which you've pulled it (e.g. D:\Work\docs-seed)
- Open a terminal of your choice (e.g. gitBash)
- Run the following command by passing the MY-REPO path (Please note, that the quotes are mandatory):
```bash
sh copy_local.sh "D:\Work\xaml-docs"
```

- Go to the MY-REPO directory and execute the following bash command in the root folder again (where the **Dockerfile** is located)
```bash
sh start-docs.sh
```

In case you want to add an additional config.yml file, pass it to the above command as follows:
```bash
sh start-docs.sh _silverlight.yml
```

- This is it! You can find the documentation site on server address which is written in the terminal: *http://0.0.0.0:4000/*. If you can't open the previous URL, replace the '0.0.0.0' with 'localhost' - *http://localhost:4000*. 
> For example, for WPF documentation this would be: http://0.0.0.0:4000/devtools/wpf/

> If you want to stop the web site and the container in which it has been served, navigate to the terminal in which you've executed the previous command and press 'CTRL+C'.

#### LiveSync
To be able to monitor the changes you are making on the built documentation, execute the following command in a new terminal in the root directory of the site:
```bash
sh watch.sh
```

> **Prerequisite**: If you haven't yet, please install [Node.js](https://nodejs.org/en/).
