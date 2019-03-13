## Field Definitions

| Column | Fieldname | Description  | Rules | Example | 
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| 1 | 		articleCode			 | Customer Article Code  | 				 string with max length of **35** characters											 | Seacon-Example-Article | 
| 2 | 		internalDescription		 | Description of the Article | 				string with max length of **30** characters											 | Example Article used by Seacon | 
| 3 | 		eanNumber			 | EAN nummer | 						Positive whole number with a max value of **9999999999999**							 | 8713500010166 | 
| 4 | 		stockUnit				 | ???lowest stock unit  | 				Stock unit type,  possible options are **ea** **ct** and **pl**							 | ea | 
| 5 | 		unitPackageCode1		 | ???next possible package type | 		Stock unit type,  possible options are **ea** **ct** and **pl**							 | pl | 
| 6 | 		unitPackageCode2		 | ???next possible package type | 		Stock unit type,  possible options are **ea** **ct** and **pl**							 | ct | 
| 7 | 		unitPackageCode3		 | ???????????????? | 				Stock unit type,  possible options are **ea** **ct** and **pl**							 |   | 
| 8 | 		unitPackageCode4		 | ???????????????? | 				Stock unit type,  possible options are **ea** **ct** and **pl**							 |   | 
| 9 | 		stacking				 | ???????????????? | 				Positive whole number with a max value of **9**										 | 1 | 
| 10 | 		stackingPackageCode	 | ???????????????? | 				string with max length of **2** characters											 | pl | 
| 11 | 		nettoWeight			 | Net Article Weight in **Kg** | 			Decimal positive number with a maximum of **999999.9999** with **4** fraction digits			 | 1.000 | 
| 12 | 		languageCode			 | Language Code used for description  | 	only these options are available: **1**:Dutch,**2**:English,**4**:German					 | 1 | 
| 13 | 		descriptionPart1		 | Fields for Article Description  | 			string with max length of **30** characters											 | WMS voorbeeld artikel omschrij | 
| 14 | 		descriptionPart2		 | Fields for Article Description  | 			string with max length of **30** characters											 | ving in het Nederlands | 
| 15 | 		descriptionPart3		 | Fields for Article Description  | 			string with max length of **30** characters											 | descriptionPart3 | 
| 16 | 		descriptionPart4		 | Fields for Article Description  | 			string with max length of **30** characters											 | descriptionPart4 | 
| 17 | 		supplierSearchName	 | EAN Code Supplier Search name  | 		string with only letters (a-z) with a maximum of  **20** characters						 | Standard | 
| 18 | 		relationNumber			 | EAN Code relation number  | 			Positive whole number with a max value of **999999999999**							 | 0 | 
| 19 | 		searchString			 | EAN Code Search name  | 			string with max length of **50** characters											 |  | 
| 20 | 		packageCode			 | EAN Code package Code  | 			string with max length of **2** characters											 | pc | 
| 21 | 		eanCode				 | EAN Code   | 						Positive whole number with a max value of **99999999999999**							 | 8713500010166 | 
|   |  			**packagePattern**		 | We use 3 levels of packageing, ea (eaches),**ct**(cartons) and **pl**(pallets) starting with the smallest level | These are not required, but nice to have|
| 22 | 		packageCode			 | Package code | 						 used for the package code, allowed values are **ea** **ct** **pl**						 | ea | 
| 23 | 		numberPerUnit			 | how many Articles for this package type  | 	Positive whole number with a max value of **999999**								 | 1 | 
| 24 | 		grossWeightPerUnit		 | Gross Weight in Kg for this package type  | 	Decimal number between **-9999999999.999** and **9999999999.999** with **3** fraction digits	 | 1.110 | 
| 25 | 		length				 | Length in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| 26 | 		width				 | Width in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| 27 | 		height				 | Height in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
||			 **packagePattern**							 | 
| 28 | 		packageCode			 | Package code | 						 used for the package code, allowed values are **ea** **ct** **pl**						 | ct | 
| 29 | 		numberPerUnit			 | how many Articles for this package type  | 	Positive whole number with a max value of **999999**								 | 12 | 
| 30 | 		grossWeightPerUnit		 | Gross Weight in Kg for this package type  | 	Decimal number between **-9999999999.999** and **9999999999.999** with **3** fraction digits	 | 1.110 ??? | 
| 31 | 		length				 | Length in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| 32 | 		width				 | Width in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| 33 | 		height				 | Height in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| |			**packagePattern** |
| 34 | 		packageCode			 | Package code | 						 used for the package code, allowed values are **ea** **ct** **pl**						 | pl | 
| 35 | 		numberPerUnit			 | how many Articles for this package type  | 	Positive whole number with a max value of **999999**								 | 120 | 
| 36 | 		grossWeightPerUnit		 | Gross Weight in Kg for this package type  | 	Decimal number between **-9999999999.999** and **9999999999.999** with **3** fraction digits	 | 1.110 ??? | 
| 37 | 		length				 | Length in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| 38 | 		width				 | Width in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| 39 | 		height				 | Height in meters for this package type | 	Decimal positive number with a max value of **999.999** and **3** fraction digits in **meters**	 | 0 | 
| |			**customGoodsCode** | | These are not required, but nice to have|
| 40 | 		importTaricCode		 | Import Taric code  | 					string with max length of **22**	characters										 | 1905905500701100000000 | 
| 41 | 		exportTaricCode		 | Export Taric code  | 					string with max length of **22**	characters										 | 1905905500701100000000 | 


## Sample CSV
We have prepared a Sample CSV file, please right-click the link below and choose Save Target do download this file.

[open sample TAB separated CSV file](./article-min-tab.csv)

[open sample COMMA separated CSV file](./article-min-comma.csv)

[open sample SEMICOLON separated CSV file](./article-min-semicolon.csv)



