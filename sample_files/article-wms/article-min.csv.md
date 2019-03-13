## Field Definitions

| Column | Fieldname | Description  | Rules | Example | 
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| 1 | 		articleCode			 | Customer Article Code  | 				 string with max length of **35** characters											 | Seacon-Example-Article | 
| 2 | 		internalDescription		 | Description of the Article | 				string with max length of **30** characters											 | Example Article used by Seacon | 
| 3 | 		eanNumber			 | EAN nummer | 						Positive whole number with a max value of **9999999999999**							 | 8713500010166 | 
| 4 | 		stockUnit				 | Stockkeeping unit  | 				Stock unit type,  possible options are **ea** **ct** and **pl**							 | ea | 
| 5 | 		unitPackageCode1		 | possible package type | 		Stock unit type,  possible options are **ea** **ct** and **pl**							 | pl | 
| 6 | 		unitPackageCode2		 | possible package type | 		Stock unit type,  possible options are **ea** **ct** and **pl**							 | ct | 
| 7 | 		unitPackageCode3		 | possible package type | 				Stock unit type,  possible options are **ea** **ct** and **pl**							 |   | 
| 8 | 		unitPackageCode4		 | possible package type | 				Stock unit type,  possible options are **ea** **ct** and **pl**							 |   | 
| 9 | 		nettoWeight			 | Net Article Weight in **Kg** | 			Decimal positive number with a maximum of **999999.9999** with **4** fraction digits			 | 1.000 | 
| 10 | 		languageCode			 | Language Code used for description  | 	only these options are available: **1**:Dutch,**2**:English,**4**:German					 | 1 | 
| 11 | 		descriptionPart1		 | Fields for Article Description  | 			string with max length of **30** characters											 | WMS voorbeeld artikel omschrij | 
| 12 | 		descriptionPart2		 | Fields for Article Description  | 			string with max length of **30** characters											 | ving in het Nederlands | 
| 13 | 		descriptionPart3		 | Fields for Article Description  | 			string with max length of **30** characters											 | descriptionPart3 | 
| 14 | 		descriptionPart4		 | Fields for Article Description  | 			string with max length of **30** characters											 | descriptionPart4 | 
| 15 | 		packageCode			 | EAN Code package Code  | 			string with max length of **2** characters											 | ct | 
| 16 | 		eanCode				 | EAN Code   | 						Positive whole number with a max value of **99999999999999**							 | 8713500010166 | 
|   |  			**packagePattern**		 | We use 3 levels of packageing, ea (eaches),**ct**(cartons) and **pl**(pallets) starting with the smallest level | These are not required, but nice to have|
| 17 | 		packageCode			 | Package code | 						 used for the package code, allowed values are **ea** **ct** **pl**						 | ea | 
| 18 | 		numberPerUnit			 | how many Articles for this package type  | 	Positive whole number with a max value of **999999**								 | 1 | 
| 19 | 		grossWeightPerUnit		 | Gross Weight in Kg for this package type  | 	Decimal number between **-9999999999.999** and **9999999999.999** with **3** fraction digits	 | 2.000| 
| 20 | 		length				 | Length in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.100 | 
| 21 | 		width				 | Width in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.200 | 
| 22 | 		height				 | Height in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.150 | 
||			 **packagePattern**							 | 
| 23 | 		packageCode			 | Package code | 						 used for the package code, allowed values are **ea** **ct** **pl**						 | ct | 
| 24 | 		numberPerUnit			 | how many Articles for this package type  | 	Positive whole number with a max value of **999999**								 | 12 | 
| 25 | 		grossWeightPerUnit		 | Gross Weight in Kg for this package type  | 	Decimal number between **-9999999999.999** and **9999999999.999** with **3** fraction digits	 | 24.000 | 
| 26 | 		length				 | Length in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.500 | 
| 27 | 		width				 | Width in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.250 | 
| 28 | 		height				 | Height in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.400 | 
| |			**packagePattern** |
| 29 | 		packageCode			 | Package code | 						 used for the package code, allowed values are **ea** **ct** **pl**						 | pl | 
| 30 | 		numberPerUnit			 | how many Articles for this package type  | 	Positive whole number with a max value of **999999**								 | 120 | 
| 31 | 		grossWeightPerUnit		 | Gross Weight in Kg for this package type  | 	Decimal number between **-9999999999.999** and **9999999999.999** with **3** fraction digits	 | 240.000 | 
| 32 | 		length				 | Length in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 1.200 | 
| 33 | 		width				 | Width in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0.800 | 
| 34 | 		height				 | Height in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 1.600 | 
| |			**customGoodsCode** | | These are not required, but nice to have|
| 35 | 		importTaricCode		 | Import Taric code  | 					string with max length of **22**	characters										 | 1905905500701100000000 | 
| 36 | 		exportTaricCode		 | Export Taric code  | 					string with max length of **22**	characters										 | 1905905500701100000000 | 


## Sample CSV
We have prepared a Sample CSV file, please right-click the link below and choose Save Target do download this file.

[open sample SEMICOLON separated CSV file](./article-min-semicolon.csv)



