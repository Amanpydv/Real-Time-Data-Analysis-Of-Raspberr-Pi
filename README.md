# Real-Time-Data-Analysis-Of-Raspberr-Pi


This repository provides a comprehensive guide to real-time data analytics using **Azure Stream Analytics**, focusing on telemetry data from IoT devices like the Raspberry Pi Azure IoT Online Simulator. By integrating the simulator with Azure Stream Analytics and other Azure services, this setup demonstrates how to process data, derive insights, and visualize key metrics in real-time.

## Overview

### Features:
- Ingest telemetry data in real-time through **Azure IoT Hub**.
- Process data using SQL-like query capabilities in **Azure Stream Analytics**.
- Derive actionable insights, trigger workflows, and monitor metrics such as temperature, humidity, or device status.
- Filter, aggregate, and perform complex event processing to identify anomalies or trends instantly.
- Seamlessly integrate with Azure services such as **Power BI** and **Azure Blob Storage** for visualization and storage.

### Key Services Used:
| Service                  | Purpose                                                                                  |
|--------------------------|------------------------------------------------------------------------------------------|
| **IoT Hub**              | To ingest real-time data from the Raspberry Pi Simulator.                                |
| **Azure Stream Analytics** | To transform and synchronize data.                                                      |
| **ADLS Gen 2**           | To store the processed data.                                                             |
| **Azure Synapse Analytics** | To analyze sink data and connect with Power BI.                                         |
| **Power BI**             | To create and share dashboards for visualization.                                        |

---

## Use Case

**Objective**: Analyze telemetry data from the Raspberry Pi IoT Simulator and monitor insights on [Power BI Web](https://app.powerbi.com).

---

## Steps to Implement

### 1. Setting Up IoT Hub
1. Create an IoT Hub account in Azure.
2. Configure the IoT Hub and add a device.

### 2. Adding the IoT Simulator
1. Use the [Raspberry Pi Web Simulator](https://azure-samples.github.io/raspberry-pi-web-simulator/).
2. Copy the primary key from the IoT Hub to the simulator.
3. Run the simulator to ensure messages are being sent to the IoT Hub.

### 3. Creating a Stream Analytics Job
1. Create a **Stream Analytics Job** in Azure.
2. Define an input source in the job topology, pointing to the IoT Hub.
3. Write a query to calculate the average temperature and humidity.

### 4. Connecting to Power BI
1. On the Power BI Web, connect the output from **Stream Analytics**.
2. Visualize the data using Power BI dashboards.

### 5. Using Azure Synapse Analytics
1. Configure the output data to be stored in **ADLS Gen2**.
2. Create a linked service in **Synapse Analytics** to ingest the output data.
3. Use Synapse pipelines to convert the dataset format to **Parquet**.
4. Connect Synapse Analytics to Power BI for enhanced reporting.

---

## Power BI Dashboard
The Power BI dashboard provides:
- Real-time visualization of average temperature and humidity.
- Insights into anomalies and trends.

---

## Challenges Faced and Solutions

### Challenge 1: Output data was only available in JSON format.
**Solution**: Used a pipeline in Synapse to convert the dataset to **Parquet** format.

### Challenge 2: Unable to download Power BI desktop due to OS issues.
**Solution**: Used an Azure VM to install and run Power BI Desktop.

### Challenge 3: Could not link Synapse as an output sink in Azure Stream Analytics.
**Solution**: Due to free subscription constraints:
- Loaded data into **ADLS Gen2**.
- Created a linked service in Synapse Analytics to process the output data.

---

## Results
The project demonstrates a scalable and efficient pipeline for real-time IoT data analytics, leveraging Azure services to derive meaningful insights and create actionable dashboards.

---

## References
- [Raspberry Pi IoT Simulator](https://azure-samples.github.io/raspberry-pi-web-simulator/)
- [Azure IoT Hub Documentation](https://learn.microsoft.com/en-us/azure/iot-hub/)
- [Azure Stream Analytics Documentation](https://learn.microsoft.com/en-us/azure/stream-analytics/)
- [Power BI Documentation](https://learn.microsoft.com/en-us/power-bi/)

---

## License
This repository is licensed under the MIT License. See the `LICENSE` file for more details.
