grafana

kubectl apply -f grafana.yaml

kubectl apply -f grafana-service.yaml

Get the external IP of the Grafana service:

kubectl get svc grafana

Task: Add FluentBit as a Data Source:

    Open your web browser and enter the external IP address of the Grafana service you obtained in the previous step.
    Log in to Grafana using the default credentials (username: admin, password: admin).

Task: Configure the Data Source:

    Click on the gear icon (⚙️) in the left sidebar to open the "Configuration" menu, then select "Data Sources."
    Click on the "Add data source" button.

Task: Fill in the Data Source Details:

    Choose "Loki" as the data source type.
    In the "HTTP" section, set the URL to the FluentBit service URL. For example, http://fluentbit:2020.
    Click on "Save & Test" to test the connection to FluentBit.