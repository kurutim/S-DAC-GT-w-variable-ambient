Jupyter Notebooks Python code for paper submitted to Geoenergy Science and Engineering
Submitted June 14, 2024

Paper: Region Specific Economic Model for Solid Sorbent Direct Air Capture Using Geothermal Energy Resources (S-DAC-GT)
Authors: Timur Kuru, Keivan Khaleghi, and Silviu Livescu1

Department of Petroleum Engineering, University of Texas at Austin, United States

Program calculates region specific levelized cost of solid sorbent direct air capture system (LCOD) and CO2 intensity (units of CO2 emitted for units captured).  Updated program from prior SPE publication.  Revised version has integrated normalization for ambient temperature and humidity, with visualizations for LCOD and CO2 intensity variablity due to ambient condition variability.

Executable version of program was too large for storage in Github.  Please contact corresponding author, Timur Kuru, at tkuru@utexas.edu for access to executable version for Windows.

Program produces output charts and sensitivity analysis.  Please refer to full paper for details.  Authors are unable to share full paper prior to publishing.  

Input Parameters are described below:

Economic parameters determine the capital cost required to calculate the levelized cost of DAC (LDAC).  The two inputs are:
WACC				Weighted average cost of capital.  

Number of Years (N)		Expected lifetime of the facility in years, over which the capital costs of the project may be amortized. 

The default values used in the model are 10% for WACC and 20 years for N.  These can be customized based on the specific requirements of the DAC project.  
WACC and N are used to calculate the Fixed Charge Factor (FCF) used to amortize the capital costs of the project (Capex), used to calculate determine LCOD.  

DAC Technical Cost and Energy Parameters
The DAC process requires four input parameters.  

Capex					The estimated capital cost in USD of the DAC facility, per annual tonne of CO2 capture capacity.  The default value is $1,379 per tonne of CO2 annual capture capacity.  

Opex					The estimated operating cost in USD of the DAC facility, per tonne of CO2.  This excludes the cost of electrical and thermal energy. The default value is $56 per tonne CO2.

Electrical Energy			The estimated electrical power consumption in kWhe per tonne of CO2.  The default value is 916 kWhe per tonne of CO2.  

Thermal Energy				The estimated thermal power consumption in kWhth per tonne of CO2.  The default value is 1,447 kWhth per tonne of CO2.  

LCOD requires levelized cost of electricity (LCOE) and levelized cost of heating (LCOH).  These are determined from regional parameters covered below. 
 
Regional Parameters
LCOE and LCOH are determined regionally.  Regions have variable electric power sources, which determine CO2 emissions due to DAC.  Further, different regions have different economies, resulting in different relative capital and operating costs.  Finally, regional climates, average temperature and humidity, can impact S-DAC process efficiency, requiring different amounts of thermal energy.  Regional parameters determine the final calculated LCOD and CO2 intensity of the planned DAC facility.  The parameters are:
Natural Gas Price	Price of natural gas in USD per Mcf.  This is used to determine the LCOD scenario using natural gas as the thermal energy source.  The default value is $5, but this can change dramatically between regions, and should be based on expected future prices.

Electricity Price			Price of regional industrial electricity in USD per kWh.  The default value is $0.15.

CO2 Intensity of Electricity		The estimated CO2 emissions per MWe. This is dependent on the profile of fuel sources for the electricity used within the region.  This can be as high as 1 tonne CO2 per MWh if the source is coal.  The average for the US in 2021 was 0.40, which is the default.

Capex Multiplier			The estimated cost of capital projects within the region, relative to the US average.  The default is 1.0.

Opex Multiplier				The estimated cost of operating costs within the region, relative to the US average.  A good proxy is relative regional costs of living.  The default is 1.0.

Temperature				The average ambient regional temperature.  The default is 15°C.

Humidity				The average ambient regional humidity.  The default is 60%.

Geothermal Reservoir Depth		The depth of the geothermal reservoir has a large impact on geothermal LCOH.  Drilling depth drives the cost of injection and production wells, and pump operating costs.  The depth is in feet and measured from surface to the depth where bottom hole temperature is at least 120°C. This depth can vary substantially between regions.  The default value is 10,000 ft.  

Geothermal Reservoir
Temperature Drawdown			Thermal drawdown, or cooling, of the geothermal reservoir can happen very quickly, but will level out asymptotically, approaching a stable temperature.  This can be difficult to model, and the decline in temperature is highly dependent on well design and reservoir engineering, as well as reservoir properties.  The model anticipates geothermal brine is initially extracted at 120°C and reinjected at 80°C.  The default drawdown value is 10°C, implying the long-term geothermal brine temperature is 110°C.

CO2 Transport				Transportation cost of the captured CO2 to the permanent geological storage reservoir.  This is dependent on the proximity to the injection reservoir and the regional CO2 pipeline infrastructure.  The default is $10 per tonne CO2.  

CO2 Storage				Cost of injection and storage of CO2 into the permanent geological storage reservoir.  This is dependent on depth, size, and quality of the CO2 storage reservoir.  This is highly dependent on regional geology.  The default is $10 per tonne CO2.

Once the input parameters are entered, “Display Chart” can be selected to display the results.  

Model Outputs

The model calculates LCOD and the CO2 intensity for the three thermal energy source scenarios.  

A total of six values are calculated:
LCODfinal			Regional LCOD in USD for S-DAC scenarios using thermal energy from electricity, natural gas, and geothermal resources.

CO2 Intensity			Regional CO2 intensity for the S-DAC process using thermal energy from electricity, natural gas, and geothermal resources.

The output is consolidated into two bar graphs displayed after the user enters all required data.  The default values result in a reasonable approximation of a relatively high quality S-DAC-GT plant within the US, assuming nearby geothermal and CO2 storage resources.  

Visualization of variability due to ambient conditions: The model allows immediate visibility of the effects of temperature and humidity variability on LCOD and CO2 intensity.  This is provided by means of a heat map centered on the user defined average temperature and humidity for the region.  

Sensitivity analysis: The model also includes a fast way for the user to conduct a sensitivity analysis, given custom parameters.
