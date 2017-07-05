# Data Dictionary

## EDR Inscriptions 
Data as received by EDR

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|edr_inscriptions|integer|internal DB id
edr_id|edr_inscriptions|character(9)|(from EDR)
ancient_city|edr_inscriptions|varchar|(from EDR)
find_spot|edr_inscriptions|varchar|(from EDR)
measurements|edr_inscriptions|varchar|(from EDR)
writing_style|edr_inscriptions|varchar|(from EDR)
language|edr_inscriptions|varchar|(from EDR)
content|edr_inscriptions|text|(from EDR)
bibliography|edr_inscriptions|text|(from EDR)
numberofimages|edr_inscriptions|integer|figured out from EDR
start_image_id|edr_inscriptions|integer|figured out from EDR - probably needs to be turned into a list, as images are deleted or added; or need different info from EDR?
stop_image_id|edr_inscriptions|integer|figured out from EDR - probably needs to be turned into a list, as images are deleted or added; or need different info from EDR?
apparatus|edr_inscriptions|text|(from EDR)
apparatus_displayed|edr_inscriptions|text|apparatus,  wherever there are EDR numbers listed, converts those EDR numbers into links to that graffito on ancientgraffiti.org

## AGP Inscriptions
Data added by AGP team

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|agp_inscription_info|integer|internal DB id
edr_id|agp_inscription_info|character(9)|foreign key: refers to edr_inscriptions table
comment|agp_inscription_info|text|our thoughts about the graffito
content_translation|agp_inscription_info|text|English translation of the content (from EDR)
lang_in_english|agp_inscription_info|varchar|The name of the language used, in English
writing_style_in_english|agp_inscription_info|varchar|
height_from_ground|agp_inscription_info|varchar|
graffito_height|agp_inscription_info|varchar|
graffito_length|agp_inscription_info|varchar|
letter_height_min|agp_inscription_info|varchar|
letter_height_max|agp_inscription_info|varchar|
property_id|agp_inscription_info|integer|foreign key: refers to property
cil|agp_inscription_info|varchar|equivalent to EDR's bibliography field
langner|agp_inscription_info|varchar|equivalent to EDR's bibliography field
has_figural_component|agp_inscription_info|boolean|
individual_letter_heights|agp_inscription_info|text|
letter_with_flourishes_height_min|agp_inscription_info|varchar|
letter_with_flourishes_height_max|agp_inscription_info|varchar|
is_greatest_hit_translation|agp_inscription_info|boolean|
is_greatest_hit_figural|agp_inscription_info|boolean|
epidoc|agp_inscription_info|text|epidocified content (from EDR)
summary|agp_inscription_info|varchar|caption of graffito

## Properties

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|properties|integer|internal DB id
property_number|properties|varchar|this is the "front" door
additional_properties|properties|varchar|the other doors in the property
property_name|properties|varchar|
italian_property_name|properties|varchar|
insula_id|properties|integer|foreign key: refers to insula table


## Property types

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|propertytypes|integer|internal DB id
name|propertytypes|varchar|This is like a vocabulary -- we only allow certain names.
description|propertytypes|varchar|

## Insula

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|insula|integer|internal DB id
modern_city|insula|varchar|
name|insula|varchar|
description|insula|varchar|


## Cities

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|cities|integer|internal DB id
name|cities|varchar|
description|cities|varchar|
pleiades_id|cities|varchar|from Pleiades

## Figural Graffiti 

AGP field|AGP Table|field type|content specifications
---|---|---|---
edr_id|figural_graffiti_info|character(9)|foreign key: refers to edr_inscriptions table
description_in_latin|figural_graffiti_info|text|
description_in_english|figural_graffiti_info|text|


## Drawing Tags

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|drawing_tags|integer|internal DB id
name|drawing_tags|varchar|This is like a vocabulary -- we only allow certain names.
description|drawing_tags|varchar|


## Graffiti to Drawing Tags

AGP field|AGP Table|field type|content specifications
---|---|---|---
id|graffitotodrawingtags|integer|internal DB id
graffito_id|graffitotodrawingtags|character(9)|foreign key: refers to edr_inscriptions table
drawing_tag_id|graffitotodrawingtags|integer|foreign key: refers to drawing_tags table

## Greatest Hits Info

AGP field|AGP Table|field type|content specifications
---|---|---|---
edr_id|greatest_hits_info|character(9)|foreign key: refers to edr_inscriptions table
commentary|greatest_hits_info|text|displayed on the greatest hits page
preferred_image|greatest_hits_info|varchar|

