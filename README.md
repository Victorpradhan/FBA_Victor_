# FBA_Victor_
Flux Balance Analysis of Human Erythrocyte
ABSTRACT

The human erythrocyte has been widely used model cell for understanding many complex biochemical networks and cellular metabolisms in various species.The kinetics, topology and regulation of metabolic pathways are fundamental to our understanding of disease mechanisms. Glycolysis remain the primary metabolic pathway in erythrocyte that synthesize ATP for several cellular functions in health and disease. Defects in glycolytic enzymes are associated with many hereditary diseases, and oxygen sensing by red cell haemoglobin and its interaction with glycolytic enzymes and membrane bound protein Band III are known to influence cellular metabolism, both in health and disease states like hypoxia. Although a number of kinetic modelling and experimental approaches have been proposed to study the mechanisms of glycolysis control in circulating RBCs, there remains gaps in our understanding of how different regulatory enzymes (HK, PK, PFK etc.)  may be involved in the synthesis of many intracellular species that are thought to be associated with ATP signalling and cross-talk (between RBC and vascular cells) during hypoxia and exercise. In recent years, constraint-based modelling has gained special attention to study genome scale metabolic reconstruction and regulations in metabolisms, in various organisms. It is the ability of this platform that allows one to integrate variety of kinetic data from various metabolomics and genomic studies to mechanistically simulate the steady-state behaviour of specific pathways and their relationships in healthy vs. disease. Therefore, in this work we have used web-based open source software and kinetic data of complex regulatory glycolytic enzymes to apply constraint-based modelling approach to erythrocyte metabolism in healthy cells. Key feed-forward and feedback activations are simulated using the computational tool (JWS Online) to predict if they are consistent with data in the laboratories. Specifically, we have used two existing dynamic models of human erythrocyte glycolysis (one without pentose phosphate and nucleotide metabolism pathways and with contributions from PPP and nucleotide metabolic pathway) to compare their efficacy in capturing experimentally observed phenomena of forward activation and pH and temperature control of key enzyme activities. Web-based “JWS Online” platform was used to conduct cellular level flux balance analysis (one of the popular constraint-based approaches) to examine the effects of forward activation of PK by FBP and other metabolites.This preliminary analysis demonstrates the suitability of this approach to study enzyme-enzyme relationships that determines metabolic state of the cell during oxygen sensing. 

Model Equations:
	Hexokinase (HK):
v_HK   =          ( V_max1/K_MgATP  ([MgATP]+V_max2/V_max1   ([MgATP][Mg])/K_(MgATP,Mg) -([G6P][MgADP])/(K_eq^HK )))/((1+([MgATP])/K_MgATP )(1+([Mg])/K_(MgATP,Mg) )+([Mg])/K_Mg +(([G6P])/K_G6P +1.55)(1+([Mg])/K_Mg )+([PG23])/K_PG23 +([Mg][PG23])/(K_Mg K_MgPG23 ))		(1)

where Vmax1, and  Vmax2 represent the maximal velocity of the forward and backward reactions of HK; K_MgATP , K_(MgATP,Mg),K_(eq. )^HK,K_Mg,K_G6P 〖,K〗_PG23 and K_MgPG23 are the dissociation constants of various substrates, products and effectors associated with hexokinase (HK) and values are given in the Table. vHKis the initial velocity of HK.
	Glucose-6-phosphate isomerase (PGI):
■(v_PGI=(V_max ([G6P]-1/(K_(eq.)^PGI )[F6P]))/([G6P]+K_G6P (1+([F6P])/K_F6P ) )@@)								(2)
where Vmax represent the maximal velocity of the forward reaction of PGI,K_(eq.)^PGI, K_G6P,K_F6P are the dissociation constants of various substrates, products and effectors associated with  glucose-6-phosphate isomerase(PGI). VPGIis the initial velocity of PGI.

	Phosphofructokinase (PFK):
v_PFK=(V_max ([F6P][MgATP]-[FBP][MgADP]/(K_(eq.)^PFK  )))/([F6P]+K_F6P )([MgATP]+K_MgATP )(1+L_0  ((1+([ATP])/K_ATP )^4 (1+([Mg])/K_Mg )^4)/((1+([AMP])/K_AMP )^4 (1+([F6P])/K_F6P )^4 ))                                                          (3)
where Vmax represent the maximal velocity of the forward and backward reactions of PFK; K_MgATP , K_Mg,K_AMP ,K_ATP, K_(eq.)^PFKare the dissociation constants of various substrates, products and effectors associated with phosphofructokinase (PFK). VPFKis the initial velocity of PFK.

	Aldolase (ALD):
v_ALD=(V_max/(K_m^FBP )([FBP])-([GAP][DHAP])/(K_eq^ALD ))/(1+([FBP])/(K_m^FBP )+([GAP])/(K_i^GAP )  + ([DHAP]([GAP]+K_m^GAP ))/(K_m^DHAP*K_i^GAP )  + ([FBP][GAP])/(K_m^FBP K_ii^GAP ))						(4)  

where Vmax represent the maximal velocity of the forward and backward reactions of ALD;K_m^DHAP ,K_m^GAP 〖,K〗_m^FBP,K_(eq.)^ALD,K_i^GAP 〖,K〗_ii^GAPare the dissociation constants of various substrates, products and effectors associated with aldolase (ALD). VALDis the initial velocity of ALD.



	Triosephosphate isomerase (TPI)
■(v_TPI=(V_max ([DHAP]-1/(K_(eq.)^TPI )[GAP]))/([DHAP]+K_DHAP (1+([GAP])/K_GAP ) )@@)	              (5)
where Vmax represent the maximal velocity of the forward and backward reactions of TPI; K_DHAP, K_(eq.)^TPI,K_GAPare the dissociation constants of various substrates, products and effectors associated with triosephosphate isomerase(TPI). VTPIis the initial velocity of TPI.

	Glyceraldehydephosphate dehydrogenase (GPDH):
■(v_GPDH=(V_max/(K_NAD K_GAP K_(P_i ) ) ([NAD][GAP][P_i ]-1/(K_eq^GPDH )[PG13][NADH]))/(-1+(1+([NAD])/K_NAD )(1+([GAP])/K_GAP )(1+[P_i ]/K_(P_i ) )+(1+([NADH])/K_NADH )(1+([PG13])/K_PG13 ) )@@@@)                                                         (6)
where Vmax represent the maximal velocity of the forward and backward reactions of GPDH; K_(eq.)^GPDH ,K_GAP,K_(P_i ),K_NAD,K_NADH,K_PG13 are the dissociation constants of various substrates, products and effectors associated with Glyceraldehydephosphate dehydrogenase(GPDH). VGPDHis the initial velocity of GPDH.
	Phosphoglycerate kinase (PK):

v_PGK=(V_max/(K_MgADP K_PG13 ) ([MgADP][PG13]-1/(K_eq^PGK )[MgATP][PG3]))/(-1+(1+MgADP/K_MgADP )(1+([PG13])/K_PG13 )+(1+([MgATP])/K_"MgATP "  )(1+([PG3])/K_PG3 ) )                                                    (7)

where Vmax represent the maximal velocity of the forward and backward reactions of PGK; are the dissociation constants of various substrates, products and effectors associated with Phosphoglycerate kinase(PGK). VPGKis the initial velocity of PGK.

	2,3 Biphosphoglycerate mutase (PGM23):
■(v_PGM23=(k_PGM23 ([PG13]-1/(K_(eq.)^PGM23 )[PG23]))/(1+([PG23])/K_PG23 )@)                                                                                               (8)
where Vmax represent the maximal velocity of the forward and backward reactions of PGM23;k_PGM23 ,K_PG23,K_"eq. " ^PGM23are the dissociation constants of various substrates, products and effectors associated with 2,3 biphosphoglyceratemutase(PGM23). VPGM23is the initial velocity of PGM23.

	2,3 Biphosphoglycerate phosphatase (PGP23):
■(v_PGP23=(V_max ([PG23]-1/(K_(eq.)^PG23 )[PG3]))/([PG23]+K_PG23 )@)(9)
where Vmax represent the maximal velocity of the forward and backward reactions of PGP23; 〖,K〗_"eq. " ^PGP2,K_PG23 are the dissociation constants of various substrates, products and effectors associated with 2,3 Biphosphoglyceratephosphatase(PGP23). VPGP23is the initial velocity of PGP23.
	3-phosphoglycerate mutase (PGLM):
v_PGLM=(V_max ([PG3]-1/(K_(eq.)^PGLM )[PG2]))/([PG3]+K_PG3 (1+([PG2])/K_PG2 ) )(10)
where Vmax represent the maximal velocity of the forward and backward reactions of PGLM; K_MgATP ,K_(eq.)^PGLM,K_PG3,K_PG2 are the dissociation constants of various substrates, products and effectors associated with hexokinase (PGLM). VPGLMis the initial velocity of PGLM.			
	Enolase (ENO):
	■(V_ENO&=(V_max ([PG2]-1/(K_(eq.)^ENO )[PEP]))/([PG2]+K_PG2 (1+([PEP])/K_PEP ) )@&@&)	                 (11)
where Vmax represent the maximal velocity of the forward and backward reactions of ENO; K_PEP , K_(eq. )^ENO, K_PG2 are the dissociation constants of various substrates, products and effectors associated with enolase (ENO). VENOis the initial velocity of ENO.	
	Pyruvate kinase (PK):

v_PK=(V_max ([PEP]⋅[MgADP]-([PYR][MgATP])/K_(eq.) ))/([PEP]+K_PEP )([MgADP]+K_MgADP )(1+L_0  (1+[ATP]/K_ATP  )^4/((1+[PEP]/K_PEP )^4 (1+[FBP]/K_FBP )^4 )) 			(12)
where Vmax represent the maximal velocity of the forward and backward reactions of PK; K_MgADP , K_(eq. )^PK,K_ATP,and K_FBP,K_PEP are the dissociation constants of various substrates, products and effectors associated with pyruvate (PK). VPKis the initial velocity of PK.	
	Lactate dehydrogenase (LDH):
■(v_LDH=k(K_(eq.)^LDH [PYR][NADH]-[LAC][NAD])@)  (13)
whereK_MgATP ,,K_(eq. )^LDH, [NAD],[NADH],[LAC]are the dissociation constants of various substrates, products and effectors associated with lactate dehydrogenase(LDH). VLDHis the initial velocity of LDH.
	Adenylate kinase (AK):

V_AK=(V_max/(K_"ATP "  K_AMP ) ([MgATP][AMP]-1/(K_(eq.)^AK ) [MgADP][ADP] ))/((1+[MgATP]/K_ATP )(1+[AMP]/K_AMP )+([MgADP]+[ADP])/K_ADP +([MgADP][ADP])/(K_ADP^2 ))(14)
where Vmax represent the maximal velocity of the forward reactions of AK; K_MgATP , K_(eq. )^AK,K_ATP,K_ADP,K_AMP are the dissociation constants of various substrates, products and effectors associated with adenylate kinase(AK). VAKis the initial velocity of AK.

	ATPase:
v_"ATPase " =k[MgATP]                       (15)
k=1.26h^(-1)
Where k is the dissociation constants of various substrates, products and effectors associated with Atpase .VATPaseis the initial velocity of ATPase.
	V16
v_16  =  kMgATPdiss  (−  [ATP]  [Mg]  +  KeqMgATPdiss  [MgATP])                                        (16)
where V represent the maximal velocity of the forward of V16; are the dissociation constants of various substrates, products and effectors associated with (V16).
	V17
v_17  =  kMgADPdiss  (−  [ADP]  [Mg]  +  KeqMgADPdiss  [MgADP])                           (17)
where V represent the maximal velocity of the forward reactions of V17; are the dissociation constants of various substrates, products and effectors associated with (V17).
	V18
v_18  =  kMgAMPdiss  (−  [AMP]  [Mg]  +  KeqMgAMPdiss  [MgAMP])                        (18)
where V represent the maximal velocity of the forward reactions of V18; are the dissociation constants of various substrates, products and effectors associated with  (V18). 
	V19
v_19  =  kPS										             (19)
where V the maximal velocity of the forward reactions of V19; K_MgATP , are the dissociation constants of various substrates, products and effectors associated with  (V19).

Ordinary Differential Equation of Model Glycolysis
	d[G6P]/dt=v_HK-v_PGI-0.21
	d[F6P]/dt=v_PGI-v_PFK-0.071
	d[FBP]/dt=v_PFK-v_ALD
	d[GAP]/dt=v_ALD-v_PPI-v_GAPDH+0.071
	d[DHAP]/dt=v_VLD-v_TPI
	d[PG13]/dt=v_GAPDH-v_PGK-v_PGM23
	d[PG3]/dt=v_PGK-v_PGLM+v_PGP23
	d[PG23]/dt=v_PGM23-v_PGP23
	d[PG2]/dt=v_PGLM-v_ENO
	d[PEP]/dt=v_ENO-v_PK
	d[PYR]/dt=v_PK-v_LAC
	d[AMP]/dt=〖-v〗_AK-v_MgMP
	d[ADP]/dt=v_AK-v_MgADP
	d[ATP]/dt=v_MgATP
	d[MgAMP]/dt=v_MgAMP
	d[MgADP]/dt=v_AK-〖(v〗_PK+v_PGK-v_HK-v_PFK)+v_ATPase+v_MgADP
	d[MgATP]/dt=〖-v〗_AK+(v_PK+v_PGK-v_HK-v_PFK )-v_ATPase+v_MgATP
	d[Mg^(++) ]/dt=〖-v〗_MgAMP+v_MgADP+v_MgATP
 
Table : List of parameter values associated with glycolysis model glycolysis
Sl No.	Parameter	Value	Sl No.	Parameter	Value	Sl No.	Parameter	Value
1	KAKADP	0.11	28	KPGLMPG2	1	55	KiALDGAP	0.0572
2	KAKAMP 	0.08	29	KPGLMPG3	5	56	KiiALDGAP	0.176
3	KAKATP	0.09	30	KPGMPG23	0.04	57	KmALDDHAP	0.0364
4	KENOPEP	1	31	KPGP23	0.2	58	KmALDFBP	0.0071
5	KENOPG2	1	32	KPKATP	3.39	59	KmALDGAP	0.1906
6	KGPDHGAP	0.005	33	KPKFBP	0.005	60	L0PFK	0.001072
7	KGPDHNAD	0.05	34	KPKMgADP	0.474	61	L0PK	19
8	KGPDHNADH	0.0083	35	KPKPEP	0.225	62	Vmax1HK	15.8
9	KGPDHPG13 	0.0035	36	KTPIDHAP	0.838	63	Vmax2HK	33.2
10	KGPDHPhi	3.9	37	KTPIGAP	0.428	64	VmaxAK	1380
11	KHKG6P	0.0045	38	KeqAK	0.4582	65	VmaxALD	89.91
12	KHKMg	1.03	39	KeqALD	0.114	66	VmaxENO	1500
13	KHKMgATP	1.44	40	KeqENO	1.2	67	VmaxGPDH	4300
14	KHKMgATPMg	1.14	41	KeqGPDH	0.00109	68	VmaxPFK	239
15	KHKMgPG23	2.44	42	KeqHK	10433	69	VmaxPGI	935
16	KHKPG23	2.7	43	KeqLDH	16979	70	VmaxPGK	5000
17	KPFKAMP	0.033	44	KeqMgADPdiss	0.81	71	VmaxPGLM	2000
18	KPFKATP	0.01	45	KeqMgAMPdiss	22.2	72	VmaxPGP23	0.52
19	KPFKF6P	0.1	46	KeqMgATPdiss	0.081	73	VmaxPK	570
20	KPFKMg	0.44	47	KeqPFK	1075	74	VmaxTPI	5456.6
21	KPFKMgATP	0.069	48	KeqPGI	0.444	75	kATPase	1.26
22	KPGIF6P	0.071	49	KeqPGK	2232	76	kLDH	1000000
23	KPGIG6P	0.182	50	KeqPGLM	0.05	77	kMgADPdiss	1000000
24	KPGKMgADP	0.35	51	KeqPGM23	100000	78	kMgAMPdiss	1000000
25	KPGKMgATP	0.48	52	KeqPGP23	100000	79	kMgATPdiss	1000000
26	KPGKPG13	0.002	53	KeqPK	3349	80	kPGM23	110000
27	PGKPG3	1.2	54	KeqTPI	0.051	81	kPS	1

List of initial conditions associated with Model 1 (see table 1 of Joshi and Palson) 
Sl no.	Species Name	Initial condition (t = 0), (mM)	Sl no.	Species Name	Initial condition
(t = 0),  (mM)
1	ADP	0.19704	13	MgAMP	0.00188
2	AMP	0.05534	14	MgATP	1.4252
3	ATP	0.15312	15	NAD	0.0886
4	DHAP	0.09614	16	NADH	0.0004
5	F6P	0.02251	17	PEP	0.0076
6	FBP	0.00511	18	PG13	0.000581
7	G6P	0.05102	19	PG2	0.00793
8	GAP	0.00489	20	PG23	4.676
9	GLU	1	21	PG3	0.16473
10	LAC	1.1	22	PYR	0.01435
11	Mg	0.754	23	Phi	0.5
12	MgADP	0.18343			

RESULTS
Simulated steady state metabolite concentration and fluxes in presence and absence of forward activation by JWS using Bali et. al
Variable	With FA	Without FA
G6P		51.02	29.74
F6P	22.51	13.08
FBP	5.11	68.69
DHAP	96.14	379.1
GAP	4.89	19.32
PG13	0.581	2.31
PG23	4.676	18.164
PG3	164.73	765.54
PG2	7.93	37.93
PEP	7.6	43.52
PYR	14.35	14.35
LAC	1.1	1.1
AMP	55.34	69.49
MgAMP	1.88	2.42
ADP	197.04	213.41
MgADP	183.43	204.37
ATP	153.12	143.04
MgATP	1425.4	1369.8
Mg	754	775.7

Fluxes	With FA	Without FA
V1	1.2836	22.6553
V2	1.0736	21.6553
V3	1.1446	22.6553
V4	1.1446	22.6553
V5	1.1446	22.6553
V6	2.36021	46.3106
V7	1.86161	45.8851
V8	0.498591	0.425466
V9	0.498591	0.425466
V10	2.36021	46.3106
V11	2.36021	46.3106
V12	2.36021	46.3106
V13	2.36021	46.3106


Concentration of metabolites and Fluxes  in presence and absence of forward activation of PK by FBP.
![image](https://github.com/Victorpradhan/FBA_Victor_/assets/138599162/c9ec4610-c044-44c3-9c80-8b27b4978b45)
![image](https://github.com/Victorpradhan/FBA_Victor_/assets/138599162/5571c214-0732-4975-9658-049f02a90479)

Steady state metabolites concentration and fluxes without forward activation (as fraction of control concentration and flux) using Bali et. al
Variable	Concentration without FA
G6P	0.582908663
F6P	0.581075078
FBP	13.44227006
DHAP	3.943207822
GAP	3.950920245
PG13	3.975934
PG23	3.884516681
PG3	4.64724094
PG2	5.726315789
PEP	5.726315789
PYR	1
LAC	1
AMP	1.255692085
MgAMP	1.287234043
ADP	1.083079578
MgADP	1.114157989
ATP	0.934169279
MgATP	0.960993405
Mg	1.028779841

Fluxes	With FA	Without FA
V1	1.2836	22.6553
V2	1.0736	21.6553
V3	1.1446	22.6553
V4	1.1446	22.6553
V5	1.1446	22.6553
V6	2.36021	46.3106
V7	1.86161	45.8851
V8	0.498591	0.425466
V9	0.498591	0.425466
V10	2.36021	46.3106
V11	2.36021	46.3106
V12	2.36021	46.3106
V13	2.36021	46.3106

![image](https://github.com/Victorpradhan/FBA_Victor_/assets/138599162/0ebd94aa-f87d-4856-993b-e28a568b6fda)
![image](https://github.com/Victorpradhan/FBA_Victor_/assets/138599162/a456f260-5f07-4c0c-a7fd-625ba7de1337)

stochiometric matrix, 
![image](https://github.com/Victorpradhan/FBA_Victor_/assets/138599162/3ed1ff89-8ba0-4ceb-9ded-08e86a2109f8)
![image](https://github.com/Victorpradhan/FBA_Victor_/assets/138599162/4cc603af-ca8a-4395-822f-e482a7c6c3b3)

In this work I have explored the capability of JSW online platform using existing models of cellular metabolic pathways.
Two mathematical models RBC metabolism are implemented using JSW online platform.
FBA of RBC glycolysis revels in absence of forward activation , increase in level of PG23 could compromise ability of hemoglobin to carry oxygen.
Current approach can be applied to analyze experimental data on steady-state enzyme activities  and metabolites measured in metabolomic  assays.




