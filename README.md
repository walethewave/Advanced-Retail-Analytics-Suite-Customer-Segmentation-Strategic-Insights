# **Project Title: Exploratory Data Analysis on Market Basket Analysis and Item-Based Collaborative Filtering**

## **Introduction**
In this project, I performed an exploratory data analysis (EDA) focusing on Market Basket Analysis and Item-Based Collaborative Filtering. The objective was to uncover patterns in customer purchasing behavior and generate personalized product recommendations for the Bronze Segment.

## **Objectives**
- **Market Basket Analysis:** To identify strong associations between items purchased together, which can be used for strategic decisions like product placement and promotions.
- **Item-Based Collaborative Filtering:** To predict customer preferences based on their past purchasing behavior and the behavior of similar customers.

## **Steps Taken**

### 1. **Market Basket Analysis**
**Objective:**
To discover patterns of items frequently bought together and understand their associations.

**Process:**

- **Rule Identification:**
  - **Antecedents:** Items or item sets that lead to the purchase of another item.
  - **Consequents:** Items that are frequently bought as a result of the antecedents.

- **Metrics Used:**
  - **Support:** Measures the frequency of transactions containing the item set.
  - **Confidence:** The likelihood that a consequent item is purchased when the antecedent is present.
  - **Lift:** Indicates how much more likely the consequent is to be bought compared to its general occurrence.

- **Example Output:**
  For instance, a rule `{Bread} -> {Butter}` indicates that 20% of all transactions include bread, and when bread is bought, there’s a 75% chance butter is bought too, increasing the likelihood by 2.5 times.

**Decision-Making Applications:**
- **Product Placement:** Items frequently bought together can be placed near each other in stores.
- **Promotions:** Bundling or offering discounts on items with high lift and confidence metrics.

### 2. **Item-Based Collaborative Filtering**
**Objective:**
To create a recommendation system for customers based on items they have previously purchased.

**Process:**

- **Step 1: Co-occurrence Matrix**
  - Created a co-occurrence matrix to understand how often pairs of items are purchased together.
  - Used a pivot table to structure the data, followed by encoding the quantities into binary (1 if purchased, 0 if not).
  - The dot product of this matrix with its transpose was computed to get the co-occurrence matrix, indicating how frequently each pair of items is bought together.

- **Step 2: Identifying Similar Items**
  - Identified items that co-occur the most using the co-occurrence matrix.
  - Filtered out identical pairs (items paired with themselves) to get meaningful associations between different products.

- **Step 3: Correlation Matrix for Items**
  - Computed a correlation matrix for items to understand which products are likely to be bought together based on past customer behavior.
  - Analyzed specific products (e.g., "WHITE HANGING HEART T-LIGHT HOLDER") to identify other products that customers frequently buy with it.

- **Step 4: Personalized Recommendations**
  - Created personalized recommendations by iterating over a customer's purchase history and finding similar products using the correlation matrix.
  - Aggregated and sorted these similarities, then filtered out items the customer already bought, leaving a list of top recommendations.

**Example Output:**
Top Recommendations: Products like "WOODLAND WATER TRANSFER TATTOOS" and "LUNCH BAG BLACK SKULL" were identified as top recommendations for a customer, based on their past purchases and the co-occurrence/correlation with other items.

## **Challenges and Solutions**
- **Problem: Handling Missing Values and Deprecation Warnings**
  - Encountered warnings such as `FutureWarning` related to the deprecation of `applymap` in pandas, which I addressed by considering alternatives like `map`.
  - Managed issues with correlation calculations, where warnings indicated potential problems with degrees of freedom and invalid operations, by refining data processing steps.

## **Conclusion**
This analysis provided valuable insights into customer purchasing patterns and allowed for the development of a recommendation system tailored to individual customers' preferences. This system can help retailers make informed decisions about product placement, promotions, and inventory management.

## **Future Work**
- Consider integrating more sophisticated machine learning models to enhance the accuracy of predictions.
- Expand the analysis to other customer segments and compare the results with the Bronze segment.




## **Key Problems Solved**

### **Identifying Product Affinities**
- **Challenge:** Customers often purchase related items together, but without data-driven insights, it’s difficult to identify these relationships.
- **Solution:** Using Market Basket Analysis, I uncovered associations between products, determining which items are frequently bought together. For example, I found that customers who buy Bread are 2.5 times more likely to also buy Butter. This insight can drive strategic decisions on product placement and promotions.

### **Building a Personalized Recommendation System**
- **Challenge:** Generic recommendations fail to resonate with customers, leading to lost sales opportunities.
- **Solution:** Through Item-Based Collaborative Filtering, I developed a recommendation system that suggests products based on a customer’s purchase history and similar customer behavior. For instance, if a customer previously bought **WHITE HANGING HEART T-LIGHT HOLDER**, the system might recommend **WOODLAND WATER TRANSFER TATTOOS** as a related product.

### **Handling Data Quality Issues**
- **Challenge:** The dataset had missing values and inconsistencies, which could skew the analysis.
- **Solution:** I implemented data cleaning techniques to address these issues, ensuring that the analysis was based on accurate and complete data. This step was crucial for producing reliable recommendations and insights.

### **Optimizing Model Performance**
- **Challenge:** The initial models produced warnings and encountered issues with data processing, such as deprecation warnings and invalid operations.
- **Solution:** I refined the data processing pipeline, choosing more efficient methods and resolving warnings, which improved the model's stability and performance.

## **Business Insights Gained**
- **Strategic Product Placement:** The analysis revealed key product pairs that are frequently bought together, enabling smarter product placement strategies in stores or online platforms. For example, placing Bread near Butter could increase sales for both items.

- **Targeted Promotions:** By understanding which products are often bought together, businesses can create targeted promotions. Offering discounts on Butter when Bread is purchased could drive higher sales volumes.

- **Enhanced Customer Satisfaction:** The personalized recommendation system ensures that customers receive product suggestions that align with their interests, increasing the likelihood of repeat purchases and customer loyalty.

- **Data-Driven Decision Making:** The insights from this project empower businesses to make informed decisions about inventory management, marketing strategies, and customer engagement.

## **Project Highlights**
- **Data Preprocessing:** Cleaned and structured transaction data for analysis, ensuring accuracy and reliability in the results.
- **Market Basket Analysis:** Identified strong product associations using metrics like support, confidence, and lift.
- **Item-Based Collaborative Filtering:** Developed a recommendation system that suggests products based on item co-occurrence and correlation.
- **Visualization:** Created clear and insightful visualizations to communicate findings, making complex data understandable at a glance.
- **Problem-Solving:** Addressed challenges related to data quality, model warnings, and performance optimization to ensure the robustness of the analysis.

## **Technology Stack**
- **Python:** For data analysis and model building.
- **Pandas & NumPy:** Data manipulation and numerical computations.
- **Scikit-learn:** Machine learning algorithms for collaborative filtering.
- **Matplotlib & Seaborn:** Data visualization to showcase insights.
- **Jupyter Notebook:** For interactive data exploration and documentation.

## **Conclusion**
This project not only demonstrates my ability to perform complex data analyses but also showcases my problem-solving skills and my capacity to derive actionable business insights from raw data. The recommendation system developed here has the potential to significantly enhance customer experience and drive sales growth, making it a valuable tool for any retail business.
