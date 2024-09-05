Description: To probe *E. coli* metabolism in TXTL, we vary amounts of some metabolites in the energy 
mixture. In this experiment, we add 200ug/mL tetracycline to see if the TX trends we saw can be present
in the absence of translation. 
	We create the following solutions for our experiments: a minimal energy solution without 3-PGA 
and NTPs; ATP solution, GTP solution, NTP solution, 3-PGA solution (from Miki), pyruvate solution, 
succinate solution, and maltose solution. We also create a malachite green solution to measure mRNA 
dynamics.
	In this experiment, we perform a 3-PGA vs Magnesium panel with 5nM DNA, DAJ_MK_MY extract, and
tetracycline. The DAJ_MK_MY extract is a a dialyzed, French-pressed extract. This is a repeat of the 
20230501 expt albeit with new-ish Midiprepped DNA. 



Minimal energy solution (5.774mL/3.6):

	Component		Protocol Amount		Amount for 1604uL (/3.6)
	---------		---------------		-------------------------
	HEPES			3.6mL				1000uL
	tRNA			576uL				160uL
	CoA			576uL				160uL
	cAMP			170uL				47.22uL
	Folinic acid		288uL				80uL
	Spermidine		144uL				40uL
	NAD+			276uL				76.67uL
	H2O			144uL				40uL



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



Tetracycline (80mg/mL)

	Component		Protocol Amount
	---------		---------------	
	Tetracycline		40mg
	DMSO			0.5mL



Experiment Protocol:
	1. Prepare 80mg/mL tetracycline in DMSO. Then dilute 16X to 5 mg/mL, by combining 
		- 4uL of 80mg/mL solution with 
		- 60uL nuclease-free water
	2. Create a minimal master mix that will be added to all samples. 
	The composition is computed from the same Jupyter notebook used to create the Echo picklist.
		Component				Protocol Amount (uL)
		---------				--------------------
		Extract					469
		PEG (40%)				71
		Minimal energy sol. (24.862 x)		57
		Amino acids				355
		K (3000mM)				37.84
		Malachite Green Dye			28.38
		NTPs (500mM)				13.74
	2. We use the Echo to load whatever is not in the minimal master mix into our sample wells, as 
	   defined by our Echo picklist. We make sure to leave one well space between wells with 
	   different samples.
		Source Well		Component			Volume (uL)
		-----------	-------------------------		-----------
		    M08		3-PGA, diluted 3X to 467mM		65	
		    M09		3-PGA, diluted 3X to 467mM		30	
		    M11		Mg-glutamate, diluted 4x to 100mM	65
		    M12		Mg-glutamate, diluted 4x to 100mM	43    
		    M14		H2O					65
		    M15		H2O					65
		    M16		H2O					65
		    M17		H2O					65
	3. Load 7.26uL of minimal master mix into samples G18-G20. Also add 0.72uL nuclease-free H2O to them.
	4. Then, add 
		- 42uL 353ng/uL DNA 
		- 56.76uL 5mg/mL tetracycline 
	   and load 7.97uL minimal master mix into each sample.
	5. Perform the following BioTek protocol.
		  Start Kinetic	Runtime 18:00:00 (HH:MM:SS), Interval 0:03:00, 193 Reads	
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
	- 