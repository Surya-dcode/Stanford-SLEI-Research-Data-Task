# SLEI Research Data Task – Comprehensive Analysis

**Candidate:** Surya Doddipatla  
**Position:** Research Analyst – Stanford Latino Entrepreneurship Initiative  

---

## Executive Summary

This analysis demonstrates advanced data analysis capabilities directly applicable to SLEI's mission of understanding Latino entrepreneurship patterns. Using baseball data, I showcase analytical approaches relevant to Dr. Zárate's research:

- **International talent analysis**
- **Temporal trend identification**
- **Data infrastructure design**
- **Evidence-based policy recommendations**

Each component parallels challenges in studying Latino business success factors, geographic entrepreneurship patterns, and international talent development.

---

## Q1: Hall of Fame Players by Country Over Time

### Strategic Approach & SLEI Relevance
This mirrors SLEI's core work: tracking how international talent (Latino entrepreneurs) achieves recognition (business success) over time across regions. The same methodology can be used for:

- Latino business ownership patterns
- Venture capital access by country of origin
- Entrepreneurship success trajectories

---

### Code Implementation

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
from pathlib import Path
import warnings
warnings.filterwarnings('ignore')

plt.style.use('seaborn-v0_8-whitegrid')
sns.set_palette("husl")

# Example: Data loading function
def load_and_validate_data():
    try:
        people = pd.read_csv('people.csv')
        hall_of_fame = pd.read_csv('hall_of_fame.csv')
        
        print("Data Quality Assessment:")
        print(f"People records: {len(people):,}")
        print(f"Hall of Fame records: {len(hall_of_fame):,}")
        return people, hall_of_fame
    
    except FileNotFoundError as e:
        print(f"Data file not found: {e}")
        return None, None
