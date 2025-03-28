🚗 Used Car Sales Analysis Dashboard (2023-2024)
📄 Project Description
This project analyzes used car sales data for the year 2023-2024. The goal is to identify key market trends, pricing insights, brand-wise performance, and factors impacting used car sales. The analysis has been done using Microsoft Excel and Power BI, making the information visually appealing and business-friendly.
🛠️ Tools Used
Microsoft Excel (Data Cleaning & Basic Statistics)
Power BI (Interactive Dashboard Creation)
DAX (Data Analysis Expressions) for KPIs and Measures
📅 Data Source
The dataset contains information related to:
Brand
Model
Fuel Type
Selling Price
Mileage
Year of Sale
Count of Cars Sold
Data is collected from used car sales records for the year 2023-2024.
📊 Dashboard Overview
The Power BI Dashboard includes:
Total Cars Sold
Average Selling Price
Most Sold Brand
Average Selling Price by Brand (Bar Chart)
Fuel Type Distribution (Pie Chart)
Count of Model by Brand (Bar Chart)
Mileage vs Selling Price Analysis (Scatter Plot & Line Chart)
🔥 Key Insights
Most Sold Brand: Maruti Suzuki has the highest sales.
Total Cars Sold: 46 cars analyzed.
Average Selling Price: ₹9,75,995.72
Price Range: ₹15,000 to ₹4,25,00,000
Top Fuel Type: Petrol cars (39%) dominate the sales.
Luxury brands like Lamborghini, Rolls Royce, Bentley have high resale prices.
Cars with high mileage have lower resale value.
✅ DAX Measures Used
Total Cars Sold = SUM(used_cars_dataset_v2[AskPrice])
Average Selling Price = AVERAGE(used_cars_dataset_v2[AskPrice])
Most Sold Brand =
VAR TopBrand =
    VAR TopBrand = 
    TOPN(
        1, 
        ADDCOLUMNS(
            SUMMARIZE('used_cars_dataset_v2', 'used_cars_dataset_v2'[Brand]),
            "BrandCount", COUNTROWS(FILTER('used_cars_dataset_v2', 'used_cars_dataset_v2'[Brand] = EARLIER('used_cars_dataset_v2'[Brand])))
        ),
        [BrandCount], DESC
    )
RETURN 
    SELECTCOLUMNS(TopBrand, "Brand", 'used_cars_dataset_v2'[Brand])

📌 Conclusion
This analysis highlights the current trends in the used car market and provides key insights to stakeholders for better decision-making. It helps in understanding:
Which brands are performing well
How fuel type affects sales
Pricing patterns based on mileage and brand
The interactive dashboard enables dealers and customers to make data-driven decisions.
🚀 Future Scope
Add Year-on-Year Sales Comparison
Include Customer Demographics Analysis
Expand dataset for regional insights
Add Profit Margin analysis
