# Redefine The Metadata 

```javascript
    DATA: lo_entity     TYPE REF TO /iwbep/if_mgw_odata_entity_typ, 
           lo_property   TYPE REF TO /iwbep/if_mgw_odata_property, 
           lo_annotation TYPE REF TO /iwbep/if_mgw_odata_annotation. 

    super->define( ). 

    " Type 
     lo_entity = model->get_entity_type( iv_entity_name = 'TypeHelp'  ). 
     IF lo_entity IS BOUND. 
       lo_property = lo_entity->get_property( iv_property_name = 'Type' ). 
       IF lo_property IS NOT INITIAL. 
         lo_annotation = lo_property->/iwbep/if_mgw_odata_annotatabl~create_annotation( iv_annotation_namespace = /iwbep/if_mgw_med_odata_types=>gc_sap_namespace ). 
         lo_annotation->add( 
           EXPORTING 
             iv_key      = 'text' 
             iv_value    = 'TypeDesc' 
         ). 
       ENDIF. 
     ENDIF. 
```
