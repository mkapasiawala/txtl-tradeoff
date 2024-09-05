Description: In collaboration with William Poole and Zoila Jurado, I am doing experiments to probe cell extract metabolism.
In this experiment and subsequent experiments, we vary the amount of fuel we are using at the following levels: 5mM, 10mM,
15mM, 20mM, 30mM, and 45mM. We are effectively performing a panel of fuel vs Mg to understand the complex interplay between
fuel and magnesium. We use a Jupyter notebook to compute the final concentrations of these components in the TXTL 
reaction mixture. 
	We create the following solutions for our experiments: a minimal energy solution without 3-PGA and NTPs; ATP 
solution, GTP solution, NTP solution, 3-PGA solution (from Miki), pyruvate solution, succinate solution, and maltose
solution. We also create a malachite green solution to measure mRNA dynamics.
	In this experiment, we perform an NTP by ATP by GTP panel at fixed 0mM Mg+2 (previous optimal for other fuel 
sources at 5nM DNA, and we use a dialyzed, French-pressed extract. Here we use newly prepared batches of energy
solution and NTP solution.



Minimal energy solution (5.774mL/7.33):

	Component		Protocol Amount		Amount for 788uL (/7.33)
	---------		---------------		-------------------------
	HEPES			3.6mL				491.13uL
	tRNA			576uL				78.58uL
	CoA			576uL				78.58uL
	cAMP			170uL				23.19uL
	Folinic acid		288uL				39.29uL
	Spermidine		144uL				19.65uL
	NAD+			276uL				37.65uL
	H2O			144uL				19.65uL



GTP (760mM):

	Component		Protocol Amount		Actual amount (/4.237)
	---------		---------------		-------------------------
	GTP			   500mg			118mg
	H2O			   1245uL			294uL



CTP (621mM):

	Component		Protocol Amount		Actual amount (/1.667)
	---------		---------------		-------------------------
	CTP			   300mg			180mg
	H2O			   708uL			424.8uL



UTP (813mM):

	Component		Protocol Amount		Actual amount (/1.345)
	---------		---------------		-------------------------
	UTP			   300mg			223mg
	H2O			   480uL			357uL



NTP solution (500mM):

	Component		Protocol Amount		Actual amount (x2)
	---------		---------------		-------------------------
	ATP (540mM)			74uL			148uL
	GTP (760mM)			52.8uL			105.6uL
	UTP (813mM)			29.6uL			59.2uL
	CTP (621mM)			38.8uL			77.6uL
	KOH (15%)			60uL			120uL 



3-PGA (1400mM):

	Component		Protocol Amount
	---------		---------------	
	3-PGA			    3g
	2M Tris			    5.04mL
	H2O			    3.156mL



Malachite Green Dye (62.5mM):

	Component		Protocol Amount
	---------		---------------	
	Malachite green		0.0929g
	H2O			1050uL



Malachite Green Dye (500uM):

	Component		Protocol Amount
	---------		---------------	
	62.5mM MG (above)	8uL
	H2O			992  uL



Pyruvate (1250mM, pH ~ 7.5):

	Component		Protocol Amount
	---------		---------------	
	Pyruvate		    0.77g
	2M Tris-HCl pH 7.4	    4.257mL
	Tris base (2M)		    350uL
	KOH (5M)		    100uL



Maltose (1400mM, pH 7.44):

	Component		Protocol Amount
	---------		---------------	
	Maltose			    2.52g
	2M Tris-HCl pH 7.4	    4.305mL
	Tris base (2M)		    90uL



Succinate (1400mM, pH 7.54):

	Component		Protocol Amount
	---------		---------------	
	Succinate		    1.89g
	2M Tris-HCl pH 7.4	    5mL
	HCl			    55uL



Experiment Protocol:
	1. Create a minimal master mix that will be added to all samples. 
	The composition is computed from the same Jupyter notebook used to create the Echo picklist.
	   (228 samples * 7.169uL/sample * 1.1 excess = 1798uL)
		Component				Protocol Amount (uL)
		---------				--------------------
		Extract					828 (30 tubes)
		PEG (40%)				125.4
		Minimal energy sol. (24.862 x)		100.9 (3 tubes)
		Amino acids (6mM)			627
		K(3000mM)				66.88	
		Malachite Green Dye (500uM)		50.16		
	2. Prepare diluted NTP solutions.
		- 60uL NTPs + 110uL H2O
		- 50uL ATP + 87.5uL H2O
		- 35uL GTP + 105uL H2O
	2. We use the Echo to load whatever is not in the minimal master mix into our sample wells, as defined by
	   our Echo picklist. We make sure to leave one well space between wells with different samples.
		Source Well		Component			Volume (uL)
		-----------	-------------------------		-----------
		    P01		NTPs, diluted 2.5X to 200mM		65	
		    P02		NTPs, diluted 2.5X to 200mM		60	    
		    P04		ATP, diluted 2.75X to 196mM		65
		    P05		ATP, diluted 2.75X to 196mM		55
		    P07		GTP, diluted 4X to 190mM		65
		    P08		GTP, diluted 4X to 190mM		55
		    P10		Mg-glutamate, 100mM			42
		    P12		DNA,  425 ng/uL				65
		    P13		DNA,  425 ng/uL				32
		    P15		H2O					65
		    P16		H2O					65
		    P17		H2O					65
		    P18		H2O					65
		    P19		H2O					65
		    P20		H2O					65
		    P21		H2O					65
	3. Load 7.17uL of minimal master mix into each sample.
	4. Perform the following BioTek protocol.
		  Start Kinetic	Runtime 18:00:00 (HH:MM:SS), Interval 0:04:00							
			- Linear shake: 0:05 (MM:SS), frequency: 360 cpm (6 mm)	
			- Read MGaptmer
			  Filter Set 1							
	    			Excitation: 610,  Emission: 650							
	    			Optics: Bottom,  Gain: 150													
			  Light Source: Xenon Flash,  Lamp Energy: High							
			  Read Speed: Normal,  Delay: 100 msec,  Measurements/Data Point: 10							
			  Read Height: 9.5 mm						
    			- Read deGFP														
			  Filter Set 1							
	    			Excitation: 485,  Emission: 515							
	    			Optics: Bottom,  Gain: 61													
			  Light Source: Xenon Flash,  Lamp Energy: High							
			  Read Speed: Normal,  Delay: 100 msec,  Measurements/Data Point: 10							
			  Read Height: 7 mm

Results:
-	Noticed higher expression for higher GTP
-	Also noticed higher expression for higher ATP
-	TL prefers higher GTP than ATP (consistent with previous results, although less skewed)
