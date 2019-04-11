
# Files
  

## dist/metadata/be-dictionary.csv
Is a dataset containing every level of Belgium divisions, usefull for recoding belgian divisions levels.  
Variables: StatisticalSector,NIS9,PostCode,Municipality,NIS5,Arrondissement,NIS2,NUTS3,Province,NIS1_5,NUTS2,Region,NIS1,NUTS1  
Format: csv  


## dist/points/postal-codes.WGS84.js
Is a dataset mapping every postal code to it's coordinates  
Source: Google Maps geocoding API  
Format: JavaScript  
Geographic coordinate system: latitude & longitude  


## dist/polygons/be-provinces-unk.geo.json
Is a geojson map for plotting Provinces.  
It contains also an "UNK" (unkown) rectangle.  
Format: geojson

## dist/polygons/be_contour_lowdensity_lambert.js
Dataset containing coordinates of the contour of Belgium  
Format: JavaScript  
Geographic coordinate system: Belgian Lambert 72  
Density: 729 points

## dist/polygons/be-municip-lamberts.geo.json
Src: sh_statbel_statistical_sectors.geojson from https://statbel.fgov.be/en/open-data/statistical-sectors
Tool: https://mapshaper.org/
Operations: 
- import + check snap option
- console: 
		dissolve CD_MUNTY_REFNIS
- simplify 15%
- repair
- console: 
		rename-fields NIS5=CD_MUNTY_REFNIS
		mapshaper -o be-municip-lamberts.geo.json precision=0.0001
Size: 2.2Mb




----------------

# LINKS

- http://www.atlas-belgique.be/cms2/index.php?page=cartodata_fr
- https://ec.europa.eu/eurostat/web/gisco/geodata/reference-data/administrative-units-statistical-units/nuts#nuts16


----------------

# Explanation of Divisions, Variables and Codes

## 3 Regions
Codes : NUTS1

    BE1	 Brussels
    BE2	 Vlaanderen
    BE3	 Wallonie
    
## 10 Provinces + Brussels-capital region
Codes : NIS1.5 | NUTS2

    1     BE21  Antwerpen
    21    BE10  Brussels
    23|24 BE24  Vlaams-Brabant
    25    BE31  Brabant Wallon
    3     BE25  West-Vlaanderen
    4     BE23  Oost-Vlaanderen
    5     BE32  Hainaut
    6     BE33  Liège
    7     BE22  Limburg
    8     BE34  Luxembourg
    9     BE35  Namur
    
## 27 Arrondissements judiciaires			
## 43 Arrondissements administratifs (44 NUTS3 codes because Verviers is divided in 2 judiciary arrondissements)
Codes: NIS2 | NUTS3

	11	BE211	Antwerpen
	12	BE212	Mechelen
	13	BE213	Turnhout
	21	BE100	Brussels-Capital
	23	BE241	Halle-Vilvoorde
	24	BE242	Leuven
	25	BE310	Nivelles
	31	BE251	Brugge
	32	BE252	Diksmuide
	33	BE253	Ypres
	34	BE254	Kortrijk
	35	BE255	Oostende
	36	BE256	Roeselare
	37	BE257	Tielt
	38	BE258	Veurne
	41	BE231	Aalst
	42	BE232	Dendermonde
	43	BE233	Eeklo
	44	BE234	Gent
	45	BE235	Oudenaarde
	46	BE236	Sint-Niklaas
	51	BE321	Ath
	52	BE322	Charleroi
	53	BE323	Mons
	54	BE324	Mouscron
	55	BE325	Soignies
	56	BE326	Thuin
	57	BE327	Tournai
	61	BE331	Huy
	62	BE332	Liège
	63	BE335	Verviers_FR
	63	BE336	Verviers_GE
	64	BE334	Waremme
	71	BE221	Hasselt
	72	BE222	Maaseik
	73	BE223	Tongeren
	81	BE341	Arlon
	82	BE342	Bastogne
	83	BE343	Marche-en-Famenne
	84	BE344	Neufchâteau
	85	BE345	Virton
	91	BE351	Dinant
	92	BE352	Namur
	93	BE353	Philippeville
    
## 589 Municipalities (or entities) (since 1983)
Codes: PC | NIS5

    1000	21004	Bruxelles
	1030	21015	Schaerbeek
	1040	21005	Etterbeek
	1050	21009	Ixelles
	1060	21013	St-Gillis
	1070	21001	Anderlecht
	1080	21012	St-Jan-Molenbeek
	1081	21011	Koekelberg
	1082	21003	St-Agatha-Berchem
	1083	21008	Ganshoren
	1090	21010	Jette
	1140	21006	Evere
	1150	21019	St-Pieters-Woluwe
	1160	21002	Oudergem
	1170	21017	Watermael-Boitsfort
	1180	21016	Uccle
	1190	21007	Forest
	1200	21018	St-Lambrechts-Woluwe
	1210	21014	Saint-Josse-ten-Noode
	1300	25112	Wavre
	1310	25050	La Hulpe
	1315	25043	Incourt
	1320	25005	Beauvechain
	1325	25018	Chaumont-Gistoux
	1330	25091	Rixensart
	1340	25121	Ottignies-Louvain-la-Neuve
	1350	25120	Orp-Jauche
	1357	25118	Hélécine
	1360	25084	Perwez
	1367	25122	Ramillies
	1370	25048	Jodoigne
	1380	25119	Lasne
	1390	25037	Grez-Doiceau
	1400	25072	Nivelles
	1410	25110	Waterloo
	1420	25014	Braine-l'Alleud
	1430	25123	Rebecq
	1435	25068	Mont-Saint-Guibert
	1440	25015	Braine-le-Château
	1450	25117	Chastre
	1457	25124	Walhain
	1460	25044	Ittre
	1470	25031	Genappe
	1480	25105	Tubize
	1490	25023	Court-Saint-Etienne
	1495	25107	Villers-la-Ville
	1500	23027	Halle
	1540	23032	Herne
	1547	23009	Bever
	1560	23033	Hoeilaart
	1570	23023	Galmaarden
	1600	23077	Sint-Pieters-Leeuw
	1620	23098	Drogenbos
	1630	23100	Linkebeek
	1640	23101	Sint-Genesius-Rode
	1650	23003	Beersel
	1670	23064	Pepingen
	1700	23016	Dilbeek
	1730	23002	Asse
	1740	23086	Ternat
	1745	23060	Opwijk
	1750	23104	Lennik
	1755	23024	Gooik
	1760	23097	Roosdaal
	1770	23044	Liedekerke
	1780	23102	Wemmel
	1785	23052	Merchtem
	1790	23105	Affligem
	1800	23088	Vilvoorde
	1820	23081	Steenokkerzeel
	1830	23047	Machelen
	1840	23045	Londerzeel
	1850	23025	Grimbergen
	1860	23050	Meise
	1880	23039	Kapelle-op-den-Bos
	1910	23038	Kampenhout
	1930	23094	Zaventem
	1950	23099	Kraainem
	1970	23103	Wezembeek-Oppem
	1980	23096	Zemst
	2000	11002	Antwerpen
	2070	11056	Zwijndrecht
	2110	11050	Wijnegem
	2150	11007	Borsbeek
	2160	11052	Wommelgem
	2200	13011	Herentals
	2220	12014	Heist-op-den-Berg
	2230	13013	Herselt
	2235	13016	Hulshout
	2240	11054	Zandhoven
	2250	13029	Olen
	2260	13049	Westerlo
	2270	13012	Herenthout
	2275	13019	Lille
	2280	13010	Grobbendonk
	2290	13044	Vorselaar
	2300	13040	Turnhout
	2310	13037	Rijkevorsel
	2320	13014	Hoogstraten
	2330	13023	Merksplas
	2340	13004	Beerse
	2350	13046	Vosselaar
	2360	13031	Oud-Turnhout
	2370	13001	Arendonk
	2380	13035	Ravels
	2387	13002	Baarle-Hertog
	2390	11057	Malle
	2400	13025	Mol
	2430	13053	Laakdal
	2440	13008	Geel
	2450	13021	Meerhout
	2460	13017	Kasterlee
	2470	13036	Retie
	2480	13006	Dessel
	2490	13003	Balen
	2500	12021	Lier
	2520	11035	Ranst
	2530	11004	Boechout
	2540	11021	Hove
	2547	11025	Lint
	2550	11024	Kontich
	2560	12026	Nijlen
	2570	12009	Duffel
	2580	12029	Putte
	2590	12002	Berlaar
	2620	11018	Hemiksem
	2627	11038	Schelle
	2630	11001	Aartselaar
	2640	11029	Mortsel
	2650	11013	Edegem
	2800	12025	Mechelen
	2820	12005	Bonheiden
	2830	12040	Willebroek
	2840	11037	Rumst
	2845	11030	Niel
	2850	11005	Boom
	2860	12035	Sint-Katelijne-Waver
	2870	12030	Puurs
	2880	12007	Bornem
	2890	12034	Sint-Amands
	2900	11040	Schoten
	2910	11016	Essen
	2920	11022	Kalmthout
	2930	11008	Brasschaat
	2940	11044	Stabroek
	2950	11023	Kapellen
	2960	11009	Brecht
	2970	11039	Schilde
	2980	11055	Zoersel
	2990	11053	Wuustwezel
	3000	24062	Leuven
	3020	24038	Herent
	3040	24045	Huldenberg
	3050	24086	Oud-Heverlee
	3060	24009	Bertem
	3070	24055	Kortenberg
	3080	24104	Tervuren
	3090	23062	Overijse
	3110	24094	Rotselaar
	3120	24109	Tremelo
	3130	24007	Begijnendijk
	3140	24048	Keerbergen
	3150	24033	Haacht
	3190	24014	Boortmeerbeek
	3200	24001	Aarschot
	3210	24066	Lubbeek
	3220	24043	Holsbeek
	3270	24134	Scherpenheuvel-Zichem
	3290	24020	Diest
	3300	24107	Tienen
	3320	24041	Hoegaarden
	3350	24133	Linter
	3360	24011	Bierbeek
	3370	24016	Boutersem
	3380	24137	Glabbeek
	3390	24135	Tielt-Winge
	3400	24059	Landen
	3440	24130	Zoutleeuw
	3450	24028	Geetbets
	3460	24008	Bekkevoort
	3470	24054	Kortenaken
	3500	71022	Hasselt
	3520	71066	Zonhoven
	3530	72039	Houthalen-Helchteren
	3540	71024	Herk-de-Stad
	3545	71020	Halen
	3550	71070	Heusden-Zolder
	3560	71037	Lummen
	3570	73001	Alken
	3580	71004	Beringen
	3590	71011	Diepenbeek
	3600	71016	Genk
	3620	73042	Lanaken
	3630	73107	Maasmechelen
	3640	72018	Kinrooi
	3650	72041	Dilsen-Stokkem
	3660	71047	Opglabbeek
	3665	71002	As
	3670	72040	Meeuwen-Gruitrode
	3680	72021	Maaseik
	3690	71067	Zutendaal
	3700	73083	Tongeren
	3717	73028	Herstappe
	3720	73040	Kortessem
	3730	73032	Hoeselt
	3740	73006	Bilzen
	3770	73066	Riemst
	3790	73109	Voeren
	3800	71053	Sint-Truiden
	3830	73098	Wellen
	3840	73009	Borgloon
	3850	71045	Nieuwerkerken
	3870	73022	Heers
	3890	71017	Gingelom
	3900	72029	Overpelt
	3910	72025	Neerpelt
	3920	72020	Lommel
	3930	72037	Hamont-Achel
	3941	72038	Hechtel-Eksel
	3945	71069	Ham
	3950	72003	Bocholt
	3960	72004	Bree
	3970	71034	Leopoldsburg
	3980	71057	Tessenderlo
	3990	72030	Peer
	4000	62063	Liège
	4040	62051	Herstal
	4050	62022	Chaudfontaine
	4100	62096	Seraing
	4120	62121	Neupré
	4130	62032	Esneux
	4140	62100	Sprimont
	4160	61079	Anthisnes
	4170	62026	Comblain-au-Pont
	4180	61024	Hamoir
	4190	61019	Ferrières
	4210	61010	Burdinne
	4217	61028	Héron
	4219	64075	Wasseiges
	4250	64029	Geer
	4257	64008	Berloz
	4260	64015	Braives
	4280	64034	Hannut
	4287	64047	Lincent
	4300	64074	Waremme
	4317	64076	Faimes
	4340	62006	Awans
	4347	64025	Fexhe-le-Haut-Clocher
	4350	64063	Remicourt
	4357	64023	Donceel
	4360	64056	Oreye
	4367	64021	Crisnée
	4400	62120	Flémalle
	4420	62093	Saint-Nicolas
	4430	62003	Ans
	4450	62060	Juprelle
	4460	62118	Grâce-Hollogne
	4470	64065	Saint-Georges-sur-Meuse
	4480	61080	Engis
	4500	61031	Huy
	4520	61072	Wanze
	4530	61068	Villers-le-Bouillet
	4537	61063	Verlaine
	4540	61003	Amay
	4550	61043	Nandrin
	4557	61081	Tinlot
	4560	61012	Clavier
	4570	61039	Marchin
	4577	61041	Modave
	4590	61048	Ouffet
	4600	62108	Visé
	4607	62027	Dalhem
	4610	62015	Beyne-Heusay
	4620	62038	Fléron
	4630	62099	Soumagne
	4650	63035	Herve
	4670	62119	Blégny
	4680	62079	Oupeye
	4690	62011	Bassenge
	4700	63023	Eupen
	4710	63048	Lontzen
	4720	63040	Kelmis
	4730	63061	Raeren
	4750	63013	Bütgenbach
	4760	63012	Büllingen
	4770	63001	Amel
	4780	63067	Sankt Vith
	4790	63087	Burg-Reuland
	4800	63079	Verviers
	4820	63020	Dison
	4830	63046	Limbourg
	4837	63004	Baelen
	4840	63084	Welkenraedt
	4845	63038	Jalhay
	4850	63088	Plombières
	4860	63058	Pepinster
	4870	62122	Trooz
	4877	63057	Olne
	4880	63003	Aubel
	4890	63089	Thimister-Clermont
	4900	63072	Spa
	4910	63076	Theux
	4920	62009	Aywaille
	4950	63080	Waimes
	4960	63049	Malmedy
	4970	63073	Stavelot
	4980	63086	Trois-Ponts
	4987	63075	Stoumont
	4990	63045	Lierneux
	5000	92094	Namur
	5030	92142	Gembloux
	5060	92137	Sambreville
	5070	92048	Fosses-la-Ville
	5080	92141	La Bruyère
	5140	92114	Sombreffe
	5150	92045	Floreffe
	5170	92101	Profondeville
	5190	92140	Jemeppe-sur-Sambre
	5300	92003	Andenne
	5310	92035	Eghezée
	5330	92006	Assesse
	5340	92054	Gesves
	5350	92097	Ohey
	5360	91059	Hamois
	5370	91064	Havelange
	5377	91120	Somme-Leuze
	5380	92138	Fernelmont
	5500	91034	Dinant
	5520	91103	Onhaye
	5530	91141	Yvoir
	5537	91005	Anhée
	5540	91142	Hastière
	5550	91143	Vresse-sur-Semois
	5555	91015	Bièvre
	5560	91072	Houyet
	5570	91013	Beauraing
	5575	91054	Gedinne
	5580	91114	Rochefort
	5590	91030	Ciney
	5600	93056	Philippeville
	5620	93022	Florennes
	5630	93010	Cerfontaine
	5640	92087	Mettet
	5650	93088	Walcourt
	5660	93014	Couvin
	5670	93090	Viroinval
	5680	93018	Doische
	6000	52011	Charleroi
	6110	52048	Montigny-le-Tilleul
	6120	56086	Ham-sur-Heure-Nalinnes
	6140	52022	Fontaine-l'Evèque
	6150	56001	Anderlues
	6180	52015	Courcelles
	6200	52012	Châtelet
	6210	52075	Les Bons Villers
	6220	52021	Fleurus
	6230	52055	Pont-à-Celles
	6240	52018	Farciennes
	6250	52074	Aiseau-Presles
	6280	52025	Gerpinnes
	6440	56029	Froidchapelle
	6460	56016	Chimay
	6470	56088	Sivry-Rance
	6500	56005	Beaumont
	6530	56078	Thuin
	6540	56044	Lobbes
	6560	56022	Erquelinnes
	6567	56049	Merbes-le-Château
	6590	56051	Momignies
	6600	82003	Bastogne
	6630	81013	Martelange
	6637	82009	Fauvillers
	6640	82036	Vaux-sur-Sûre
	6660	82014	Houffalize
	6670	82037	Gouvy
	6680	82038	Sainte-Ode
	6687	82005	Bertogne
	6690	82032	Vielsalm
	6700	81001	Arlon
	6717	81003	Attert
	6720	85046	Habay
	6730	85039	Tintigny
	6740	85009	Etalle
	6747	85034	Saint-Léger
	6750	85026	Musson
	6760	85045	Virton
	6767	85047	Rouvroy
	6769	85024	Meix-devant-Virton
	6780	81015	Messancy
	6790	81004	Aubange
	6800	84077	Libramont-Chevigny
	6810	85007	Chiny
	6820	85011	Florenville
	6830	84010	Bouillon
	6840	84043	Neufchâteau
	6850	84050	Paliseul
	6860	84033	Léglise
	6870	84059	Saint-Hubert
	6880	84009	Bertrix
	6887	84029	Herbeumont
	6890	84035	Libin
	6900	83034	Marche-en-Famenne
	6920	84075	Wellin
	6927	84068	Tellin
	6929	84016	Daverdisse
	6940	83012	Durbuy
	6950	83040	Nassogne
	6960	83055	Manhay
	6970	83049	Tenneville
	6980	83031	La Roche-en-Ardenne
	6987	83044	Rendeux
	6990	83028	Hotton
	6997	83013	Erezée
	7000	53053	Mons
	7040	53084	Quévy
	7050	53044	Jurbise
	7060	55040	Soignies
	7070	55035	Le Roeulx
	7080	53028	Frameries
	7090	55004	Braine-le-Comte
	7100	55022	La Louvière
	7120	56085	Estinnes
	7130	56011	Binche
	7140	56087	Morlanwelz
	7160	52010	Chapelle-lez-Herlaimont
	7170	52043	Manage
	7180	52063	Seneffe
	7190	55050	Ecaussinnes
	7300	53014	Boussu
	7320	51009	Bernissart
	7330	53070	Saint-Ghislain
	7340	53082	Colfontaine
	7350	53039	Hensies
	7370	53020	Dour
	7380	53068	Quiévrain
	7387	53083	Honnelles
	7390	53065	Quaregnon
	7500	57081	Tournai
	7600	57064	Péruwelz
	7610	57072	Rumes
	7620	57093	Brunehaut
	7640	57003	Antoing
	7700	54007	Mouscron
	7730	57027	Estaimpuis
	7740	57062	Pecq
	7750	57095	Mont-de-l'Enclus
	7760	57018	Celles
	7780	54010	Comines-Warneton
	7800	51004	Ath
	7830	55039	Silly
	7850	55010	Enghien
	7860	55023	Lessines
	7870	53046	Lens
	7880	51019	Flobecq
	7890	51017	Ellezelles
	7900	57094	Leuze-en-Hainaut
	7910	51065	Frasnes-lez-Anvaing
	7940	51012	Brugelette
	7950	51014	Chièvres
	7970	51008	Beloeil
	8000	31005	Brugge
	8020	31022	Oostkamp
	8210	31040	Zedelgem
	8300	31043	Knokke-Heist
	8340	31006	Damme
	8370	31004	Blankenberge
	8377	31042	Zuienkerke
	8400	35013	Oostende
	8420	35029	De Haan
	8430	35011	Middelkerke
	8450	35002	Bredene
	8460	35014	Oudenburg
	8470	35005	Gistel
	8480	35006	Ichtegem
	8490	31012	Jabbeke
	8500	34022	Kortrijk
	8520	34023	Kuurne
	8530	34013	Harelbeke
	8540	34009	Deerlijk
	8550	34042	Zwevegem
	8560	34041	Wevelgem
	8570	34002	Anzegem
	8580	34003	Avelgem
	8587	34043	Spiere-Helkijn
	8600	32003	Diksmuide
	8610	32011	Kortemark
	8620	38016	Nieuwpoort
	8630	38025	Veurne
	8640	33041	Vleteren
	8647	32030	Lo-Reninge
	8650	32006	Houthulst
	8660	38008	De Panne
	8670	38014	Koksijde
	8680	32010	Koekelare
	8690	38002	Alveringem
	8700	37015	Tielt
	8710	37017	Wielsbeke
	8720	37002	Dentergem
	8730	31003	Beernem
	8740	37011	Pittem
	8750	37018	Wingene
	8755	37012	Ruiselede
	8760	37007	Meulebeke
	8770	36007	Ingelmunster
	8780	37010	Oostrozebeke
	8790	34040	Waregem
	8800	36015	Roeselare
	8810	36011	Lichtervelde
	8820	31033	Torhout
	8830	36006	Hooglede
	8840	36019	Staden
	8850	37020	Ardooie
	8860	34025	Lendelede
	8870	36008	Izegem
	8880	36010	Ledegem
	8890	36012	Moorslede
	8900	33011	Ieper
	8920	33040	Langemark-Poelkapelle
	8930	34027	Menen
	8940	33029	Wervik
	8950	33039	Heuvelland
	8957	33016	Mesen
	8970	33021	Poperinge
	8980	33037	Zonnebeke
	9000	44021	Gent
	9060	43018	Zelzate
	9070	44013	Destelbergen
	9080	44034	Lochristi
	9090	44040	Melle
	9100	46021	Sint-Niklaas
	9120	46003	Beveren
	9140	46025	Temse
	9150	46013	Kruibeke
	9160	46014	Lokeren
	9170	46020	Sint-Gillis-Waas
	9180	44045	Moerbeke
	9185	44073	Wachtebeke
	9190	46024	Stekene
	9200	42006	Dendermonde
	9220	42008	Hamme
	9230	42025	Wetteren
	9240	42028	Zele
	9250	42023	Waasmunster
	9255	42004	Buggenhout
	9260	42026	Wichelen
	9270	42010	Laarne
	9280	42011	Lebbeke
	9290	42003	Berlare
	9300	41002	Aalst
	9340	41034	Lede
	9400	41048	Ninove
	9420	41082	Erpe-Mere
	9450	41024	Haaltert
	9470	41011	Denderleeuw
	9500	41018	Geraardsbergen
	9520	41063	Sint-Lievens-Houtem
	9550	41027	Herzele
	9570	45063	Lierde
	9600	45041	Ronse
	9620	41081	Zottegem
	9630	45065	Zwalm
	9660	45059	Brakel
	9667	45062	Horebeke
	9680	45064	Maarkedal
	9690	45060	Kluisbergen
	9700	45035	Oudenaarde
	9750	45057	Zingem
	9770	45017	Kruishoutem
	9790	45061	Wortegem-Petegem
	9800	44011	Deinze
	9810	44048	Nazareth
	9820	44043	Merelbeke
	9830	44064	Sint-Martens-Latem
	9840	44012	De Pinte
	9850	44049	Nevele
	9860	44052	Oosterzele
	9870	44081	Zulte
	9880	44001	Aalter
	9890	44020	Gavere
	9900	43005	Eeklo
	9910	44029	Knesselare
	9920	44036	Lovendegem
	9930	44080	Zomergem
	9940	44019	Evergem
	9950	44072	Waarschoot
	9960	43002	Assenede
	9970	43007	Kaprijke
	9980	43014	Sint-Laureins
	9990	43010	Maldegem

## 1146 Postal codes
## 2663 Sections (= old municipalities between 1961 and 1983)
## 19781 statistical sectors
Codes: NIS9
