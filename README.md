**1. Mapping Anomalies (Geographic Geocoding)** Puerto Rico was incorrectly geocoded near Colombia. While defining a 'Country' column and geographic hierarchy resolved this in the standard Map visual, after the Azure Maps upgrade, the anomaly reappeared.

**2. Model Optimization & Storage Limits**
The original file size (47 MB) prevented GitHub deployment. By utilizing DAX Studio (VertiPaq Analyzer), I identified that 99.72% of the metadata was consumed by ~2,500 unused high-precision columns. I implemented a Reference Table strategy in Power Query, disabling the load for the 'heavy' original table while retaining only essential features.

**3. Visualizing Historical Trends (Dynamic Slicing)**
**Issue:** The Year Slicer on Page 2 presented a scaling challenge. Without a fixed Y-axis maximum, the chart would auto-scale, causing the data to look "chopped" or distorted rather than providing a comfortable, consistent view for the user.
**Solution:** I locked the Y-axis maximum to maintain a consistent visual baseline. While this limits the dynamic scaling of the Year Slicer, it ensures the user is not misled by a prematurely cut axis.

**Limitation:** I explored using the Play Axis for animation but discovered a limitation where the area shade (fill) below the line was not rendered during playback. I ultimately chose a standard slicer to prioritize visual clarity and a polished aesthetic.
