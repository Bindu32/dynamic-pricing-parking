# 🚗 Dynamic Pricing for Urban Parking Lots

**Summer Analytics 2025 Capstone Project**  
Hosted by: Consulting & Analytics Club × Pathway

## 📌 Problem Statement

Urban parking lots face inefficient use when prices are static. This project builds a dynamic pricing engine using real-time data and ML-inspired logic to make smarter pricing decisions for urban parking lots.

---

## ⚙️ Tech Stack

- Python (NumPy, Pandas)
- Google Colab
- Matplotlib / Bokeh (for visualization)
- Pathway (for real-time simulation)
- GitHub (version control & sharing)

---

## 🧠 Models Implemented

### 🔹 Model 1: Baseline Linear Model
- Uses only **Occupancy** and **Capacity**
- Increases price linearly as occupancy increases
- Acts as a reference model
- Formula:
  \[
  P_{t+1} = P_t + \alpha \cdot \left(\frac{\text{Occupancy}}{\text{Capacity}}\right)
  \]

![Screenshot 2025-07-06 185642](https://github.com/user-attachments/assets/163da5c9-df6b-46dc-b31b-4524853ba5af)

---

### 🔹 Model 2: Demand-Based Pricing Model
- Uses multiple real-world features:
  - Occupancy / Capacity
  - Queue Length
  - Traffic Level (low/medium/high)
  - Vehicle Type (car, bike, truck)
  - Special Day Indicator (0 or 1)
- Computes a weighted demand score using:
  \[
  \text{Demand} = \alpha \cdot \left(\frac{\text{Occupancy}}{\text{Capacity}}\right) + \beta \cdot \text{QueueLength} - \gamma \cdot \text{TrafficLevel} + \delta \cdot \text{IsSpecialDay} + \epsilon \cdot \text{VehicleTypeWeight}
  \]
- Normalized and used to adjust the base price:
  \[
  \text{Price} = 10 \cdot (1 + \lambda \cdot \text{NormalizedDemand})
  \]
- Ensures smooth price changes and bounds (between \$5 and \$20)

- ![Screenshot 2025-07-06 185707](https://github.com/user-attachments/assets/23cb5031-9d6f-4f38-a8a0-766452887471)


---

### 🔹 Model 3: Competitive Pricing Model (Advanced & Optional)
- Builds on top of Model 2 by incorporating **competition** between nearby lots
- Steps:
  1. Calculates **geographic distance** between parking lots using Haversine formula
  2. Identifies **nearby competitors within 1 km**
  3. Compares each lot's price to the **average price of competitors**
  4. Adjusts price accordingly:
     - If competitors are **cheaper**, reduce price slightly
     - If competitors are **more expensive**, increase price
- Final price is stored as `CompAdjustedPrice`

> This model simulates real-world competitive behavior and makes pricing more adaptive and business-aware.

---



---

## 📈 Visualizations

- **Matplotlib/Bokeh** for:
  - Stimulated Live Price
  - ![Screenshot 2025-07-05 233835](https://github.com/user-attachments/assets/a38d33f4-cf85-4c91-9680-de76ba2534b8)

  - Real Time Price
  - ![Screenshot 2025-07-06 185838](https://github.com/user-attachments/assets/29cfd4d6-f651-4baf-8a81-cc097a41ad3c)


---

## 🔄 Architecture Flow

![ChatGPT Image Jul 6, 2025, 07_30_15 PM](https://github.com/user-attachments/assets/c4f74bac-38b5-4461-884b-7a65bc4eeefa)



---

## Dashboard
Parking Lot Price Dashboard

![Screenshot 2025-07-05 234642](https://github.com/user-attachments/assets/cbd673cf-2cfe-4a53-9612-fa53740ef38e)

Comparison: Demand vs Competitive

![Screenshot 2025-07-05 235522](https://github.com/user-attachments/assets/cb12b765-df91-426a-88a2-4fea065743e2)




## 🧮 Machine Learning Concepts Used

- Feature Engineering
- Heuristic Modeling (Rule-based)
- Normalization
- Weighted Demand Calculation
- Time-series Analysis (occupancy over time)

---

## 🧪 How to Run

1. Clone this repo or open `Capstone_Project.ipynb` in Google Colab
2. Upload the dataset file when prompted
3. Run each section of the notebook
4. View real-time price changes and plots

---

## ✅ Features Achieved

- ✅ Dynamic price changes using real-time features
- ✅ 3 pricing models (Baseline → Demand → Competition)
- ✅ Realistic caps and smooth transitions
- ✅ Dashboard with dropdown to explore each parking lot
- ✅ Interactive visualizations using Panel + Bokeh
- ✅ Ready to deploy using Pathway streaming (simulated in Colab)


## ✍️ Author

👩🏻‍💻 **Bindu Sri**  
Summer Analytics 2025 Participant  
https://github.com/Bindu32

---
