# Google Analytics Customer Lifetime Value Prediction

## Overview
This notebook predicts customer lifetime value (CLV) for newly acquired e-commerce customers using Google Analytics 360 data. It estimates future revenue from customers within 90 days of acquisition to optimize digital advertising campaigns.

## Data Source
- **Dataset**: Google Analytics 360 sample data (Google Merchandise Store)
- **Platform**: Google BigQuery
- **Scope**: US-based customers with acquisitions before May 1, 2017

## Key Objectives
1. **Training Data**: Identify first-time purchasers and extract session-level features
2. **Feature Engineering**: Create binary and categorical features from user behavior, device, and geographic data
3. **Target Variable**: Revenue generated 8-90 days after customer acquisition
4. **Prediction**: Estimate future revenue one week post-acquisition to identify high-value customers

## Data Flow
1. Identify customers' first purchase sessions (before 05/01/2017)
2. Extract session-level metrics:
   - Transaction revenue
   - Visit frequency & page views
   - Time spent on site
   - Device type (mobile vs. desktop)
   - Browser & OS information
3. Capture subsequent engagement within 7 days of first purchase
4. Measure target revenue (days 8-90 post-acquisition)
5. Split into training, validation, and holdout test sets

## Features Used
- **Engagement Metrics**: Time on site, page views, visit numbers
- **Device & Browser**: Chrome, Safari, mobile indicator, OS type
- **Geographic**: California, New York, Bay Area indicators
- **Traffic Channel**: Referral, organic search, direct, paid search
- **Temporal**: Day of week, quarter indicators

## Model Application
Combines three revenue components for acquisition optimization:
- Revenue from first transaction
- Additional week 1 post-purchase revenue
- Predicted revenue (days 8-90)

This holistic value metric allows advertising platforms to optimize campaigns toward higher-value customer acquisition.

## Note
This notebook is intended as a starting point example and does not represent best practices for production modeling.
