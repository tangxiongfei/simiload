# Simiload

Simulation of different load shedding strategies. The high level architecture is as follows:

![image](https://user-images.githubusercontent.com/6955854/45006533-66a14d80-afc7-11e8-95a8-88c9c13546d9.png)

# Running

**Simulation server:**
- `make` compiles `server.go` and runs a container, within the metrics cluster network, with the simulation server at: `localhost:8080`

**Metrics cluster:**
- `make metrics` starts a metrics collection cluster, the Grafana frontend is at: `localhost:3000`

**Load Generation:**
- To generate some load use: `go run generate.go -config flash_sale.json "http://localhost:8080"`

**Dashboard:**
- Configure a Grafana data source of type `prometheus`. The API URL is `http://simiload_prometheus_1:9090`
- Import the dashboard stored in `dashboard.json` file in the repo

I used the logs for quick development:
![image](https://user-images.githubusercontent.com/6955854/45006491-39549f80-afc7-11e8-8225-0cadca0cee56.png)

And metrics for tuning:
<img width="1622" alt="screen shot 2018-09-07 at 7 07 06 am" src="https://user-images.githubusercontent.com/6955854/45215847-accb0b00-b26c-11e8-9e2c-da5e6890ad7f.png">
<img width="1624" alt="screen shot 2018-09-07 at 7 06 44 am" src="https://user-images.githubusercontent.com/6955854/45215849-accb0b00-b26c-11e8-8e7c-6950fe34e134.png">

