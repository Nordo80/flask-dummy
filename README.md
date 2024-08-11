# Flask-Dummy

Welcome to the `flask-dummy` repository! 🎉

This project showcases a Flask application that integrates with the Grafana ecosystem to send, filter, and visualize logs. The logs are initially sent to Grafana Alloy, then filtered and forwarded to Grafana Loki for storage. Finally, these logs are displayed in Grafana dashboards.

## 📊 Process Flow Diagram
![image](https://github.com/user-attachments/assets/3c8bdad7-57e0-4bae-94c6-da028a35de9d)

1. **Flask Application**: Sends logs to Grafana Alloy via GRPC on port `4317`.
2. **Grafana Alloy**: Filters the logs and sends them to Grafana Loki on port `3100`.
3. **Grafana Loki**: Serves as the data source for Grafana, where all logs are visualized on the "Flask App" dashboard.

## 🚀 Services and Ports
- **Flask Application**: `8080`
- **Grafana Alloy**: `12345`
- **Grafana Loki**: `3100`
- **Grafana**: `3000`

## 🛠️ Requirements
To run this project, you'll need:
- **Docker**: Ensure Docker is installed (tested on version `24.0.5`).
- **Linux**: The setup was tested on `RHEL7`.

## 🧪 How to Test
1. Clone this repository:
   ```bash
   git clone https://github.com/Nordo80/flask-dummy.git
   cd flask-dummy
2. Run docker command:
   ```bash 
   docker compose up
3. Navigate to localhost:8080/get (Flask app)
   * Its needed to generate the log
4. Navigate to localhost:3000 (Grafana)
5. Go to Dashboards => Flask app
![grafana](https://github.com/user-attachments/assets/7a37ee3f-4be2-405e-8545-8587e7348d98)


## 🔧 Additional
A plugin has been installed for Grafana that allows visualizing logs from the Loki datasource in a separate panel. To use this feature:
1. Navigate to **Explore** → **Logs**.
2. Select **Loki** as the datasource to view logs in the dedicated panel.
![additiona_grafana](https://github.com/user-attachments/assets/781c7dbe-2902-4cff-a4d1-250301e1da5a)

