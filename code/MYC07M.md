*------------------------------------------------------------------------
* C07MA & C07MD N TYPICAL MODEL
*
* RELEASE 3.2 (FOR MORE INFORMATION, READ THE MODELS.INFO FILE)
* 1, Nature NDMOS model added,
* Subcircuit NNDMOS4 defining the NNDMOS model
* 2, polydiode model added, model name is DPL.
*
* Handled by Raul Morais November, 2002
* Data from Document DS13296_V03.PDF (SPICE Models)
*------------------------------------------------------------------------
* Model NA 
*------------------------------------------------------------------------
*
*
*------------------------------------------------------------------------
* Model DNPLUS (N+/PWELL Diode Model)
*------------------------------------------------------------------------
.MODEL DNPLUS
* MOS level2 & ST typ
*+D IS=3E-7 ISW=6E-11 CJO=2.74E-4 M=0.520 CSO=4.937E-10 MS=0.352 VJ=0.8
* typ
+D IS=3E-7 ISW=6E-11 CJO=5E-4 M=0.35 CSO=2.8E-10 MS=0.21 VJ=0.8
*
*------------------------------------------------------------------------
* Model DPL (Polydiode) - Not Used
*------------------------------------------------------------------------
* Polydiode model copied from I2T
*
*.MODEL DPL D 
*+ IS = 3.9e-13 		RS = 936 				N = 1.656 
*+ BV=6.775				EG = 0.468 				XTI = 9.75e-5
*
* NNDMOS model
*** Subcircuit defining the NNDMOS - Typical model
*
*
*** NNDM (MOS) and Djunc (nwell/psub diode) models
*
.MODEL Djunc D (
+IS=1E-15				CJ=7.8901E-5			MJ=0.27412
+PB=0.42842				CJSW=7.3315E-10		MJSW=0.25301
+FC=0.99232)
*
*.MODEL NNDM NMOS LEVEL = 12
*+TOX = 175E-10			XJ = 0.05E-6			NFS = 1.9E+11
*+VTO = 0.6703916		NSUB = 7.35E+16		DELTA = 1.7
*+UO = 430				UCRIT = 1.08E+5		UEXP = 0.124
*+RSH = 520				LD = 0					WD = 0.05E-6
*+LAMBDA = 0.006375	JS = 1E-3				LIS = 2
*+ISTMP = 10				IENH = 2					CJ = 5E-4
*+MJ = 0.35				CJSW = 2.8E-10			MJSW = 0.21
*+PB = 0.73				FC = 0.5					CGSO = 4E-10
*+CGDO = 2.5E-10		KF = 3E-28				AF = 1
*+XL = 0					XW = 0					NLEV = 0
*+ALEV = 0				TCV = -1.542092E-3
*
*------------------------------------------------------------------------
* C07MA & C07MD P TYPICAL MODELS
*
* RELEASE 3.1(FOR MORE INFORMATION, READ THE MODELS.INFO FILE)
*
* Handled by Raul Morais
* Data from Document DS13296_V03.PDF (SPICE Models)
*
*------------------------------------------------------------------------
*
*------------------------------------------------------------------------
* Model DPPLUS 
*------------------------------------------------------------------------
.MODEL DPPLUS 
* ST and Alcatel Microelectronics level 2 typ
*+D IS=2E-8 ISW=7E-11 CJO=7.27E-4 M=0.568 CSO=1.831E-10 MS=0.377 VJ=0.8
* Consistent with MOS data
+D LEVEL=3 IS=2E-8 ISW=7E-11 CJO=6.0E-4 M=0.51 CSO=3.6E-10 MS=0.35 VJ=0.8
+ TREF=27
*------------------------------------------------------------------------

*------------------------------------------------------------------------
*
* CMOS07M N TYPICAL MODELS
*
* Release 3.0
*
* Handled by Raul Morais November, 2002
*
* Data from File : "Alcatel\mod\ntyp.md" 
*------------------------------------------------------------------------
* Model ND
*------------------------------------------------------------------------
.MODEL  nmos   nmos  LEVEL=3   
+ TOX=175E-10    		XJ=0.05U       		NFS=1.9E11     
+ VTO=0.77       		NSUB=7.35E16   		DELTA=0.85
+ UO=466         		THETA=0.07     		RSH=520      
+ KAPPA=0.001    		ETA=0.0052     		VMAX=1.7E5
+ LD=0U          		WD=0.05U       		JS=1E-3        
*+ LIS=2          	ISTMP=10
+ CJ=5.0E-4      		MJ=0.35        		CJSW=2.8E-10   
+ MJSW=0.21				PB=0.73        		FC=0.5         		
+ CGSO=4E-10     		CGDO=4E-10				KF=3E-28
+ AF=1
*+ IENH=2
*------------------------------------------------------------------------
* the following parameters are specific for Eldo / Hspice
*------------------------------------------------------------------------
+ XL=0U          		XW=0U          		NLEV=0.0
*------------------------------------------------------------------------
* the following parameters are specific for Anasim
*------------------------------------------------------------------------
*+ VJMAXT=5.8     	VJMINT=-300M   		VDSMAXT=5.8
*+ VGMAXT=5.8     	VBMAXT=10M     		VBMINT=-10M
*+ VDMAXL4=0U			LMIN=0.7U      		LMAX=0.7U
*+ WMIN=4U        	WMAX=10M
*------------------------------------------------------------------------
*
* CMOS07M P TYPICAL MODELS
*
* Release 3.0
*
* Handled by Raul Morais November, 2002
* Data from File : "Alcatel\mod\ptyp.md" 
*------------------------------------------------------------------------
* Model PHD
*------------------------------------------------------------------------
.MODEL  pmos   pmos  LEVEL=3   
+ TOX=180E-10    		XJ=0.025U      		NFS=8.9E10     
+ VTO=-1         		NSUB=3.5E16    		DELTA=0.8
+ UO=156         		THETA=0.13     		RSH=870      
+ KAPPA=0.001    		ETA=0.03       		VMAX=7.2E5
+ LD=-0.005U     		WD=0.075U      		JS=1E-3
*+ LIS=2          	ISTMP=10
+ CJ=6.0E-4      		MJ=0.51        		CJSW=3.6E-10   
+ MJSW=0.35				PB=0.90        		FC=0.5
+ CGSO=1E-10     		CGDO=1E-10				KF=5E-30
+ AF=1
*+ IENH=2
*------------------------------------------------------------------------
* the following parameters are specific for Eldo / Hspice
*------------------------------------------------------------------------
+ XL=0U          		XW=0U          		NLEV=0.0
*------------------------------------------------------------------------
* the following parameters are specific for Anasim
*------------------------------------------------------------------------
*+ VJMAXT=5.8     	VJMINT=-300M   		VDSMAXT=5.8
*+ VGMAXT=5.8     	VBMAXT=5.8     		VBMINT=-300M
*+ VDMAXL4=0U			LMIN=0.7U      		LMAX=0.7U
*+ WMIN=4U        	WMAX=10M
*------------------------------------------------------------------------
.MODEL VPNP460 PNP IS=230E-18 BF=22.5 VAF=50 XTB=2
* CMOS07M P TYPICAL MODELS
*
* Release 3.0
*
*
*
*
* Handled by Luis Goncalves Jun 2013
* Data from File : "Alcatel\mod\ptyp.md" 
* Keep Model PHD and ND for compatibility in previous designs
* SAme as models nmos an d pmos previous described
*------------------------------------------------------------------------
*------------------------------------------------------------------------
* CMOS07M TYPICAL MODELS
*
* Release 3.0
*
.MODEL  ND   NMOS   LEVEL=3   
+ TOX=175E-10    XJ=0.05U       NFS=1.9E11     
+ VTO=0.77       NSUB=7.35E16   DELTA=0.85
+ UO=466         THETA=0.07     RSH=520      
+ KAPPA=0.001    ETA=0.0052     VMAX=1.7E5
+ LD=0U          WD=0.05U       JS=1E-3        
*+ LIS=2          ISTMP=10
+ CJ=5.0E-4      MJ=0.35        CJSW=2.8E-10   MJSW=0.21
+ PB=0.73        FC=0.5         CGSO=4E-10     CGDO=4E-10
+ KF=3E-28       AF=1
*+ IENH=2
* the following parameters are specific for Eldo / Hspice
+ XL=0U          XW=0U          NLEV=0.0
* the following parameters are specific for Anasim
*+ VJMAXT=5.8     VJMINT=-300M   VDSMAXT=5.8
*+ VGMAXT=5.8     VBMAXT=10M     VBMINT=-10M    VDMAXL4=0U
*+ LMIN=0.7U      LMAX=0.7U      WMIN=4U        WMAX=10M
*
*
*
.MODEL  PHD   PMOS   LEVEL=3   
+ TOX=180E-10    XJ=0.025U      NFS=8.9E10     
+ VTO=-1         NSUB=3.5E16    DELTA=0.8
+ UO=156         THETA=0.13     RSH=870      
+ KAPPA=0.001    ETA=0.03       VMAX=7.2E5
+ LD=-0.005U     WD=0.075U      JS=1E-3
*+ LIS=2          ISTMP=10
+ CJ=6.0E-4      MJ=0.51        CJSW=3.6E-10   MJSW=0.35
+ PB=0.90        FC=0.5         CGSO=1E-10     CGDO=1E-10
+ KF=5E-30       AF=1
*+ IENH=2
* the following parameters are specific for Eldo / Hspice
+ XL=0U          XW=0U          NLEV=0.0
* the following parameters are specific for Anasim
*+ VJMAXT=5.8     VJMINT=-300M   VDSMAXT=5.8
*+ VGMAXT=5.8     VBMAXT=5.8     VBMINT=-300M   VDMAXL4=0U
*+ LMIN=0.7U      LMAX=0.7U      WMIN=4U        WMAX=10M
