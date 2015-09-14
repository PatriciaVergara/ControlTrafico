# Servicios Videos Online Control de Trafico

Servicio de Camaras de Control de Trafico, es posible obtener grabaciones de una camara en particular

## Coleccion de camaras [/camaras]
### Listado de todas las camaras [GET]
+ Response 200  (application/json)

         {
            "camaras": "Mis Camaras disponibles",
            "Camaras": [
                { "id":"123_a", "marca":"Samsung HD", "IP:"192.168.1.14","longitud":"-73.98551", "latitud":"40.75793"
                },
                { "id":"123_b", "marca": "Sony HD", "IP":"192.168.1.23", "longitud":"-73.99951", "latitud":"40.75897"    
                }, 
                { "id":"123_c", "marca":" Sony HD", "IP":"192.168.1.20", "longitud": "-73.98500", "latitud":"40.74593"
                },
                {"id":"123_d","marca":"Go Pro HD", "IP":"192.168.115", "longitud":"-73.92351", "latitud":"40.776993"
            ]
        }
        
        
## Agregar Camara [/camara/{IDCamara}]        


        
### Agregar Camara [POST]
+   Request (application/json)
        
        

        {
            "marca":"Go Pro HD", 
            "IP":"192.168.119", 
            "longitud":"-73.92341", 
            "latitud":"40.776393"
        }
        
+   Response 200 (aplication/json)
        

        {
           "IDCamara":"123_e"
           "marca":"Go Pro HD", 
            "IP":"192.168.119", 
            "longitud":"-73.92341", 
            "latitud":"40.776393" 
        }
        
        

    
## Collecion de Videos [/videos/{IDCamara}]
+ parameters 
    + IDCamara(string) - ID de una camara 

### Listado de todos los videos de una Camara[GET]

+ Response 200 (application/json)

        
            {
                "videos": "Videos de la camara",
                "Video" :[
                    {
                        "IDvideo": "1",
                        "inicio transmision":"01/09/2015",
                        "tamaño":"30 mb"
                        "url" :"/videos/123_a/1"
                    }, {
                        "IDvideo": "2",
                        "inicio transmision":"02/09/2015",
                        "tamaño":"10 mb"
                        "url" : "/videos/123_a/2"
                    }, {
                        "IDvideo": "3",
                        "inicio transmision": "03/09/2015",
                        "tamaño":"500 mb"
                        "url":"/videos/123_a/3"
                    },{ "IDvideo":"4",
                        "inicio transmision":"04/09/2015"
                        "tamaño":"760 mb"
                        "url":"/videos/123_a/4"
                    }
                    ]
            }
        

## Eliminar un video de una carama [/camaras/videos/{idvideo}]
+ parameter
    + idvideo (string) -Id de un video 

### Eliminar un Video [DELETE]
+ response 200 (application/json)
    

        {
            "Hecho":"true"
            "message":"El video ha sido eliminado" 
         }


        
## Busqueda de una camara en particular [/camaras/{IDcamara}]
+ parameters
    + IDcamara(string) - ID de una camara 

### Buscar Camara [GET]
+ Response 200 (application/json)

        {
            "IDcamara": "123_a",
            "marca":"Samsung HD", 
            "IP:"192.168.1.14",
            "longitud":"-73.98551", 
            "latitud":"40.75793"
        }

+ Response 400 (application/json)

  
            {
                "Error": "No existe camara con esa identificación",
                
            }
## Reproducir un video [/camaras/videos/{idvideos}/reproducciones]
+ parameters
    + idvideo(string) - Id de un video
    

### Reproducir un video  [GET]   
+ Response 200 (aplication/json)
            
        {
            "idvideo":"1"
            "fecha_grabacion":"01/09/2015"
            "source":"/camaras/videos/1/reproducciones"
         }

+ Response 400 (aplication/json)

        {
            "Error":"No se encuentra el video solicitado"
        }

## Editar una camara [/camaras/{IDCamara}]
+ parameters
    + IDCamara (string) - Id de un video

### Editar una camara [PATCH]
+ Request (aplication/json)

        
        {  
               
               "IP":"192.168.145",
                "marca" :"AOC HD"
            
        }

+ Response 200
    
       
         {

            "IDcamara": "123_a",
            "marca" :"AOC HD",
            "IP":"192.168.145",
            "longitud":"-73.98551", 
            "latitud":"40.75793"
        }

+ Response 400 

        {
        "Error":"No se pudo realizar la actulizacion"
        }
    
