# Developer Instructions

  There is no difference from installing our project from the original Augur file due to us not changing the databases.  The only thing you have to change about installing out project from the original Augur project is to fork our project instead of the original Augur repo.
  
  
Steps:

1. Create a ec2 instance, make sure to put your key-pair in a place you will remember and give it a name that you will remember. For ease of use, Putting your github access token and key-pair in the same place is helpful.
2. Go into the directory that your key-pair is installed
3. SSH into your instance
4. Install all dependencies for Augur

    #Install NodeSource
  
    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -

    #Install NodeJS
  
    sudo apt-get install -y nodejs

    #Install MariaDB (if needed on the same machine for the GHTorrent/msr14 dataset)
  
    sudo apt-get install -y mariadb-server

    #Install Anaconda
  
    curl https://repo.anaconda.com/archive/Anaconda3-5.1.0-Linux-x86_64.sh > Anaconda.sh
    chmod +x Anaconda.sh

    #You must agree to Anaconda's license terms to proceed
  
    ./Anaconda.sh -b
    rm Anaconda.sh
    
  
  5. Clone your github repo into your ec2 instance
  
     #This is the main difference from installing for the original project

     git clone https://github.com/computationalmystic/augur-group29.git

     #Assume you are in the root from which you cloned augur

     cd augur ## To get to augur root, where the make files live

     #Install the Python and Node tools and libraries needed

     sudo make install-dev # some libraries require a root install.

     #Re-install augur project (-e flag makes it so you can modify the backend without re-installing over and over)

     #* In the augur root folder *

     pip install -e .

  6. Configure your Augur.config.json file with your github access token
  
     #for "GitHub": {
        "apikey": "GitHub API Key"
     },
    
       Place your access token into the qoutes saying github api key
       
  7. Start the Server
  
       cd into your group-29 directory
       
       run make dev-start if you don't want to monitor your server
       
       run make dev if you want to restart the server and run again, also will be able to monitor the server
       
       run make-dev stop if you want to stop running the server
    
    
