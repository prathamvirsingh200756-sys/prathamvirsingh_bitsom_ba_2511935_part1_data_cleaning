# Cleaning Log
Issues found: missing region, ship mode, discounts, duplicates, inconsistent text and dates.
Actions: standardized text, filled missing region/ship_mode as Unknown, parsed dates, calculated metrics.
Business rules: missing discount->0 when sales fields valid; negative/>1 discount invalid; cancelled/failed/refunded tracked separately.
Assumptions: discount range 0-1.
Records removed: exact duplicates count recorded, not silently removed.
Records flagged: warnings/invalid in data_quality_flag.
Limitations: automated standardization may not catch all semantic inconsistencies.
