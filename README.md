# Run MS SQL Server on PKS as a POD

Step 1: create a secret
        
        > kubectl create secret generic mssql --from-literal=SA_PASSWORD="xxxxxxxxxxxxx"

Step 2: Create Persistent Volume Claim
        
        > kubectl apply -f pvc.yml
        
Step 3: Create MS SQL Server deployment
        
        > kubectl apply -f mssql-deployment.yml
        
Step 4: Run the following commands
        
        curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
        
        curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list | sudo tee /etc/apt/sources.list.d/
        
        apt-get update
        
        apt-get install mssql-tools unixodbc-dev
        
        sudo apt-get install mssql-tools unixodbc-dev
        
Step 5: Connect to MS SQL Server database

        sqlcmd -S xx.xx.xx.xx -U sa -P "xxxxxxxxxxxxxxx"
