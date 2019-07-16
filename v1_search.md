---
layout: page
title: Endpoints - /v1/search
navigation: 3
---

<style>
	.inner a {
		color: royalblue;
		font-weight: bold;
	}
	.inner code {
		font-size: 100%;
	}
	.navigation li {
		padding: 0.3vh;
	}
	.sidebar {
		min-width: 300px;
	}
	.sidebar .sidebar-main {
	    height: calc(100% - 50px);
	    overflow-y: auto;
	}
	@media (max-width: 745px) {
		.sidebar .sidebar-main {
		    height: calc(100% - 320px);
		}
	}
</style>

<br>

## Search

This endpoint is used to find information and the correct IDs of supported objects, including planets, asteroids, stars, hypotheticals, arabic parts, and more

<br>

### Parameters

| Parameter | Type | Descripton |
|---|---|---|
| query | string | The search term |
| [type](#type) | string | Optional. Filter results by object type |

<br>

### Parameters - Type
{:id="type"}

| Type | Descripton |
|---|---|
| P | Planets, lunar nodes and other objects |
| A | Asteroids |
| S | Stars |
| H | Hypothetical planets |
| C | Comets |
| L | Arabic parts/lots |

<br>

### Response

| key | Type | Description |
|---|---|---|
| [status](/astrologico/res_status.html) | string | Contains the response status |
| [error](/astrologico/res_status.html) | string | Contains the error message in case of error |
| display | string | Number of displayed results and total results |
| [results](#results) | array | Array of results (max 100) |

<br>

### Response - Results
{:id="results"}

The results field is an array of objects which contain the following fields.

| key | Type | Description |
|---|---|---|
| name | string | Object name |
| names | array | Array of names for objects with multiple names (returned for stars and arabic parts only) |
| designations | array | Array of official designations (returned for stars only) |
| code | string | Object ID to use with other endpoints |
| type | string | Object type |
| formula | string | The object formula (returned for arabic parts only) |
| reverse | boolean | Whether the formula is automatically reversed for night charts (returned for arabic parts only) |

<br>

### Sample Request

```
GET

https://api.astrologico.org/v1/search?key=APIKEY&query=eris
```

```
POST

url: "https://api.astrologico.org/v1/search",
header: {
	Authorization: APIKEY
}
body: {
	query: "eris"
}
```

<br>

### Sample Response

```
{
	"status":"OK",
	"display":"22 of 22",
	"results":[
		{
			"name":"Eris",
			"type":"Asteroid",
			"code":"A136199"
		},
		{
			"name":"Neris",
			"type":"Asteroid",
			"code":"A237845"
		},
		{
			"name":"Verish",
			"type":"Asteroid",
			"code":"A84225"
		},
		{
			"name":"Amneris",
			"type":"Asteroid",
			"code":"A871"
		},
		{
			"names":["7 Crateris","Alkes","Alpha Crateris"],
			"designations":["PLX 2562","* alf Crt","* 7 Crt","BD-17 3273","Ci 20 602","FK5 1283","GC 15106","GCRV 6795","GEN# +1.00095272","HD 95272","HIC 53740","HIP 53740","HR 4287","IRAS 10573-1801","IRC -20221","JP11 2016","LTT 4040","N30 2586","NLTT 25942","PMC 90-93 884","PPM 223763","ROT 1641","SAO 156375","SKY# 21011","TD1 15285","UBV 10058","UBV M 16693","YZ 108 4363","[GS83] 123","uvby98 100095272","2MASS J10594651-1817560","PLX 2562.00","TYC 6079-1901-1","RAVE J105946.5-181756","WEB 9736","Gaia DR2 3553136288323783680"],
			"type":"High proper-motion Star",
			"code":"S2726"
		},
		{
			"name":"Ronperison",
			"type":"Asteroid",
			"code":"A121633"
		},
		{
			"names":["11 Crateris","Alsharasif","Beta Crateris"],
			"designations":["2RXF J111139.3-224936","PLX 2605","* bet Crt","* 11 Crt","2RE J1111-224","2RE J111139-224901","BD-22 3095","CD-22 8743","CPD-22 4900","FK5 421","GC 15385","GCRV 6877","GEN# +1.00097277","GJ 416.1","GJ 9352","GSC 06649-01274","HD 97277","HIC 54682","HIP 54682","HR 4343","IRAS 11091-2233","JP11 2035","N30 2631","PMC 90-93 303","PPM 258664","RBS 948","RE J111140-224934","RE J1111-224","ROT 1664","SACS 244","SAO 179624","SKY# 21333","TD1 15445","TYC 6649-1274-1","UBV 10207","UBV M 16858","YZ 112 8674","uvby98 100097277","2MASS J11113949-2249325","PLX 2605.00","1RXS J111140.4-224933","2EUVE J1111-22.8","EUVE J1111-22.8","RX J1111.7-2250","WD 1109-225","WEB 9872","Gaia DR2 3537996837843690496"],
			"type":"Spectroscopic binary",
			"code":"S184"
		},
		{
			"names":["12 Crateris","Delta Crateris","Labrum"],
			"designations":["PLX 2630","* del Crt","* 12 Crt","BD-13 3345","FK5 426","GC 15567","GCRV 6931","GEN# +1.00098430","HD 98430","HIC 55282","HIP 55282","HR 4382","IRAS 11168-1430","IRC -10253","JP11 2050","LTT 4188","N30 2656","NLTT 26998","PMC 90-93 308","PPM 224248","RAFGL 1477","ROT 1683","SACS 248","SAO 156605","SKY# 21547","TD1 15534","UBV M 16975","UBV 10301","YZ 104 4461","YZ 0 5361","[HFE83] 790","2MASS J11192047-1446427","PLX 2630.00","TYC 5514-1423-1","WEB 9958","Gaia DR2 3561350430457462144"],
			"type":"High proper-motion Star",
			"code":"S267"
		},
		{
			"names":["13 Crateris","Lambda Crateris"],
			"designations":["PLX 2638","* lam Crt","* 13 Crt","BD-17 3367","FAUST 2888","GC 15644","GCRV 6951","GEN# +1.00098991","GSC 06088-02156","HD 98991","HIC 55598","HIP 55598","HR 4395","IRAS 11208-1830","LTT 4214","N30 2667","NLTT 27228","PPM 224336","ROT 1693","SAO 156646","SBC7 430","SKY# 21649","TD1 15585","TYC 6088-2156-1","UBV 10334","UBV M 17023","YZ 0 5952","YZ 108 4483","uvby98 100098991","2MASS J11232192-1846479","PLX 2638.00","1RXS J112321.1-184646","EC 11208-1830","RAVE J112321.9-184648","WISEA J112321.64-184648.4","WEB 9993","Gaia DR2 3546303712614228736"],
			"type":"High proper-motion Star",
			"code":"S329"
		},
		{
			"names":["14 Crateris","Epsilon Crateris"],
			"designations":["* eps Crt","* 14 Crt","BD-10 3260","GC 15665","GCRV 6962","GEN# +1.00099167","GSC 05512-01389","HD 99167","HIC 55687","HIP 55687","HR 4402","IRAS 11220-1035","IRC -10254","PPM 224361","RAFGL 1483","ROT 1697","SAO 156658","SKY# 21670","TYC 5512-1389-1","UBV 10345","UBV M 17041","YZ 0 5049","YZC 11 4280","2MASS J11243658-1051334","WEB 10009","Gaia DR2 3589693744276900224"],
			"type":"Star",
			"code":"S396"
		},
		{
			"names":["15 Crateris","Gamma Crateris"],
			"designations":["PLX 2644","* gam Crt","* 15 Crt","BD-16 3244","CSI-16 3244 1","FAUST 2891","FK5 431","GC 15669","GCRV 6963","GEN# +1.00099211J","HD 99211","HIC 55705","HIP 55705","HR 4405","JP11 2058","N30 2673","PMC 90-93 311","PPM 224369","ROT 1698","SACS 252","SAO 156661","SKY# 21677","TD1 15605","UBV 10348","UBV M 17044","YZ 107 4487","PLX 2644.00","TYC 6088-2155-1","AKARI-IRC-V1 J1124528-174102","IRAS 11223-1724","IRAS F11223-1724","UCAC3 145-133485","UCAC4 362-059873","2MASS J11245298-1741025","WISE J112452.89-174102.2","CSI-16 3244 2","ADS 8153 AB","IDS 11199-1708 AB","CCDM J11249-1741AB","WDS J11249-1741AB","** HJ 840","uvby98 100099211","WEB 10012","Gaia DR2 3546521385853638912"],
			"type":"Double or multiple star",
			"code":"S451"
		},
		{
			"names":["16 Crateris","Kappa Crateris"],
			"designations":["IRAS 11246-1204","AKARI-IRC-V1 J1127094-122124","1RXS J112709.5-122113","2MASS J11270953-1221241","* kap Crt","* 16 Crt","BD-11 3098","CCDM J11272-1221A","CSI-11 3098 1","FK5 2914","GC 15714","GCRV 6980","GEN# +1.00099564","GSC 05512-01093","HD 99564","HIC 55874","HIP 55874","HR 4416","IDS 11221-1148 A","N30 2685","PPM 224419","SAO 156685","SKY# 21740","TD1 15636","TYC 5512-1093-1","UBV 10369","UBV M 17079","YZC 11 4285","uvby98 100099564","WDS J11272-1221A","WEB 10040"],
			"type":"High proper-motion Star",
			"code":"S508"
		},
		{
			"names":["17 Crateris"],
			"designations":["* 17 Crt","ADS 8202 AB","CD-28 8928","CSI-28 8928 23","HIC 56280","HIP 56280","IDS 11273-2843","SRS 42516","SRS 42517","WDS J11323-2916AB","ADS 8202","CCDM J11323-2916AB","** H 96","uvby98 100100287","1RXS J113216.6-291538","GEN# +1.00100287","IRAS 11297-2859","AKARI-IRC-V1 J1132162-291542"],
			"type":"Double or multiple star",
			"code":"S569"
		},
		{
			"names":["21 Crateris","Theta Crateris"],
			"designations":["* tet Crt","* 21 Crt","BD-08 3202","FK5 1299","GC 15921","GCRV 7056","GEN# +1.00100889","GSC 05510-01508","HD 100889","HIC 56633","HIP 56633","HR 4468","IRAS 11341-0931","JP11 2077","N30 2712","PMC 90-93 896","PPM 194645","ROT 5564","SACS 257","SAO 138296","SKY# 21988","TD1 15748","TYC 5510-1508-1","UBV 10459","YZ 99 4329","uvby98 100100889","2MASS J11364090-0948079","WEB 10181","Gaia DR2 3587107658569000960"],
			"type":"High proper-motion Star",
			"code":"S832"
		},
		{
			"names":["24 Crateris","Iota Crateris"],
			"designations":["* iot Crt","* 24 Crt","BD-12 3466","CCDM J11387-1312AB","GC 15977","GCRV 7080","GEN# +1.00101198J","GJ 3677","GSC 05516-01578","HD 101198","HIC 56802","HIP 56802","HR 4488","IDS 11336-1239 AB","IRAS 11361-1255","PPM 224699","SAO 156802","SKY# 22049","SRS 10479","TD1 15777","TYC 5516-1578-1","UBV 10513","YZC 11 4328","2MASS J11384002-1312071","WDS J11387-1312AB","** KUI 58AB","uvby98 100101198","WEB 10226","Gaia DR2 3585098090614578688"],
			"type":"High proper-motion Star",
			"code":"S968"
		},
		{
			"names":["27 Crateris","Zeta Crateris"],
			"designations":["PLX 2713","* zet Crt","* 27 Crt","BD-17 3460","FK5 1301","GC 16112","GCRV 7119","GEN# +1.00102070","GSC 06096-02032","HD 102070","HIC 57283","HIP 57283","HR 4514","IRAS 11422-1804","IRC -20231","JP11 2085","N30 2737","PMC 90-93 898","PPM 224852","ROT 1740","SACS 258","SAO 156869","SKY# 22207","TD1 15837","TYC 6096-2032-1","UBV 10584","UBV M 17341","YZ 0 5959","YZ 108 4595","2MASS J11444576-1821025","PLX 2713.00","** HDS 1658","WDS J11448-1821AB","CCDM J11448-1821AB","WEB 10302","Gaia DR2 3544125550016418048"],
			"type":"Double or multiple star",
			"code":"S1088"
		},
		{
			"names":["30 Crateris","Eta Crateris"],
			"designations":["PLX 2759","* eta Crt","* 30 Crt","BD-16 3358","CSV 101231","FAUST 2962","FK5 1309","GC 16319","GCRV 7199","GEN# +1.00103632","GSC 06094-01532","HD 103632","HIC 58188","HIP 58188","HR 4567","IRAS 11534-1652","N30 2773","NSV 5392","PMC 90-93 906","PPM 225124","ROT 1760","SACS 263","SAO 156988","SKY# 22477","SV* ZI 908","TD1 15953","TYC 6094-1532-1","UBV 10718","UBV M 17517","YZ 106 4653","[DBA2001] FA46","uvby98 100103632","2MASS J11560095-1709029","PLX 2759.00","GJ 9382","WEB 10416","Gaia DR2 3568190457934308608"],
			"type":"High proper-motion Star",
			"code":"S1260"
		},
		{
			"names":["31 Crateris"],
			"designations":["SBC9 698","* 31 Crt","BD-18 3295","EC 11582-1922","FAUST 2981","FK5 2961","GC 16423","GCRV 7222","GEN# +1.00104337","GSC 06097-01648","HD 104337","HGAM 608","HIC 58587","HIP 58587","HR 4590","MCW 552","N30 2790","PPM 225249","ROT 1769","SAO 157042","SBC7 448","SKY# 22600","TD1 16009","TYC 6097-1648-1","V* TY Crv","YZ 109 5217","[DBA2001] FA29","uvby98 100104337","2MASS J12005117-1939325","ALS 14812","WEB 10456","Gaia DR2 3518794554458428160"],
			"type":"Spectroscopic binary",
			"code":"S1305"
		},
		{
			"names":["Psi Crateris"],
			"designations":["ADS 8086 AB","BD-17 3321","CCDM J11125-1830AB","CSI-17 3321 1","EC 11100-1813","FAUST 2844","GC 15405","GEN# +1.00097411J","GSC 06087-01749","HD 97411","HIC 54742","HIP 54742","HR 4347","PPM 224074","SAO 156528","SKY# 21356","TD1 15451","TYC 6087-1749-1","UBV M 16873","UBV 10218","YZ 108 4424","2MASS J11123037-1829590","WDS J11125-1830AB","** BU 220","** RST 8086","* psi Crt","uvby98 100097411"],
			"type":"Double or multiple star",
			"code":"S6121"
		},
		{
			"name":"Diannerister",
			"type":"Asteroid",
			"code":"A28688"
		},
		{
			"names":["17 Crateris B"],
			"designations":["* 17 Crt B","ADS 8202 B","CCDM J11323-2916B","CD-28 8928B","CSI-28 8928 22","GC 15830","GCRV 7023","HD 100286","HR 4443","PPM 259117","SAO 179967","YZ 118 7577","uvby98 100100286","WDS J11323-2916B","TYC 6663-1171-1","UCAC3 122-146256","2MASS J11321604-2915480","GEN# +1.00100286","WEB 10119","Gaia DR2 3482326708703712640"],
			"type":"High proper-motion Star",
			"code":"S571"
		},
		{
			"names":["17 Crateris A"],
			"designations":["Gaia DR2 3482326708703712896","TYC 6663-1169-1","WEB 10120","CCDM J11323-2916A","WDS J11323-2916A","HD 100286J","* 17 Crt A","ADS 8202 A","CD-28 8928A","CSI-28 8928 21","GC 15831","GCRV 7024","HD 100287","HR 4444","PPM 259116","SAO 179968","SKY# 21886","UBV M 17157","YZ 118 7578","uvby98 100100287 A","2MASS J11321641-2915396"],
			"type":"High proper-motion Star",
			"code":"S570"
		}
	]
}
```

<br><br><br>
