FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Servicios Videos Online Control de Trafico

Servicio de Camaras de Control de Trafico, es posible obtener grabaciones de una camara en particular



## Coleccion de camaras [/v2/camaras]
CAMARAS <br>
Atributos<br>
·ID: identificador unico de una camara <br>
·Marca: marca comercial de la camara<br>
·IP: direccion fisica de la camara<br>
·Longitud: ubicacion longitudinal de la camara<br>
·Latitud: ubucacion latitud de la camara<br>
### Listado de todas las camaras [GET]
+ Response 200  (application/json)

         {
            "camaras": "Mis Camaras disponibles",
            "Camaras": [
                { "id":"123_a", "marca":"Samsung HD", "IP:"192.168.1.14","longitud":"-73.98551", "latitud":"40.75793", "configuracion": { "brillo":"199", "color":"rgb (0,0,0)", "contraste":"134"},
                },
                { "id":"123_b", "marca": "Sony HD", "IP":"192.168.1.23", "longitud":"-73.99951", "latitud":"40.75897", "configuracion": { "brillo":"199", "color":"rgb (0,0,0)", "contraste":"134"},    
                }, 
                { "id":"123_c", "marca":" Sony HD", "IP":"192.168.1.20", "longitud": "-73.98500", "latitud":"40.74593","configuracion": { "brillo":"199", "color":"rgb (0,0,0)", "contraste":"134"},
                },
                {"id":"123_d","marca":"Go Pro HD", "IP":"192.168.115", "longitud":"-73.92351", "latitud":"40.776993", "configuracion": { "brillo":"199", "color":"rgb (0,0,0)", "contraste":"134"},
            ]
        }
        
        
## Agregar Camara [/v2/camaras/{IDcamaras}]     
        
### Agregar Camara [POST]
+   Request (application/json)
        
        

        {
            "marca":"Go Pro HD", 
            "IP":"192.168.119", 
            "longitud":"-73.92341", 
            "latitud":"40.776393", "configuracion": { "brillo":"199", "color":"rgb (0,0,0)", "contraste":"134"},
        }
        
+   Response 200 (aplication/json)
        

        {
           "IDCamara":"123_e"
           "marca":"Go Pro HD", 
            "IP":"192.168.119", 
            "longitud":"-73.92341", 
            "latitud":"40.776393" , "configuracion": { "brillo":"199", "color":"rgb (0,0,0)", "contraste":"134"},
        }
        
        

    
## Collecion de Videos [/v2/videos/{IDCamara}?sort]



VIDEOS <br>
Atributos<br>
·ID: identificador unico del video<br>
·Inicio de transmision: inicio de transmision del video<br>
·tamaño: peso del video<br>
·url: ubicacion del video<br>
       

+ parameters 
    + IDCamara(string) - Identificador unico de una camara ,
    + sort (string) - ordena por un atributo en especial, ejemplo tamaño, inicio de transion

### Listado de todos los videos de una Camara[GET]

+ Response 200 (application/json)

        
            {
                "videos": "Videos de la camara",
                "Video" :[
                    {
                        "IDvideo": "1",
                        "inicio transmision":"01/09/2015",
                        "tamaño":"30 mb"
                        "url" :"/v2/videos/123_a/1"
                    }, {
                        "IDvideo": "2",
                        "inicio transmision":"02/09/2015",
                        "tamaño":"10 mb"
                        "url" : "/v2/videos/123_a/2"
                    }, {
                        "IDvideo": "3",
                        "inicio transmision": "03/09/2015",
                        "tamaño":"500 mb"
                        "url":"/v2/videos/123_a/3"
                    },{ "IDvideo":"4",
                        "inicio transmision":"04/09/2015"
                        "tamaño":"760 mb"
                        "url":"/v2/videos/123_a/4"
                    }
                    ]
            }
        

## Eliminar un video de una carama [/v2/camaras/videos/{idvideo}]
+ parameter
    + idvideo (string) -Identificador unico de un video 

### Eliminar un Video [DELETE]
+ response 200 (application/json)
    

        {
            "Hecho":"true"
            "message":"El video ha sido eliminado" 
         }


        
## Busqueda de una camara en particular [/v2/camaras/{IDcamara}]
+ parameters
    + IDcamara(string) - Identificador unico de una camara 

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
## Reproducir un video [/v2/camaras/videos/{idvideos}/reproducciones]
+ parameters
    + idvideo(string) - Identificador unico de un video 
    

### Reproducir un video  [GET]   
+ Response 200 (aplication/json)
            
        {
            "idvideo":"1"
            "fecha_grabacion":"01/09/2015"
            "source":"/v2/camaras/videos/1/reproducciones"
         }

+ Response 400 (aplication/json)

        {
            "Error":"No se encuentra el video solicitado"
        }

## Editar una camara [/v2/camaras/{IDCamara}]
+ parameters
    + IDCamara (string) - Identificador unico de un video 

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
    

    
## Grabacion de videos en unidades de almacenamiento [/v2/gabraciones-videos/{idgrabacion}]


GRABACION DE VIDEOS <br>
Atributos<br>
·idgrabacion: identificador unico de la grabacion <br>
·tasa: tasa de vehiculos<br>
·formato_video: formato de grabacion del video<br>
·secuencias: cantidad de secuencias grabadas<br>
·inicio_grbacion: Fecha de inicio de la grabacion<br>   
·video: objeto video

+ parameter
    + idgrabacion(int) - Identificador unico de la grabacion

###  Estado grabacion de un video en un dispositivo de almacenamiento [GET]
+ response 200 (aplication/json)
        
        {

            "idgrabacion":"1",
            "tasa": "",
            "formato_video":"mpeg",
            "secuencias":"344",
            "inicio_grabacion":"01/09/2015",
            "video" : {  "IDvideo": "1",
                        "inicio transmision":"01/09/2015",
                        "tamaño":"30 mb"
                        "url" :"/v2/videos/123_a/1" }




        }
+ response 400
 
        {

        "Error":"Video no encontrado",
         }
         
         
## Grabacion de nuevo video [/v2/grabaciones-videos/{idvideo}]

### Nuevo video Grabado en dispositivo de almacenamiento [POST]

+   Request (application/json)
        
        

        {
            "tasa": "",
            "formato_video":"mpeg",
            "secuencias":"344",
            "inicio_grabacion":"01/09/2015",
        }
        
+   Response 200 (aplication/json)
        

        {
           "idvideo":"2"
           "tasa": "",
            "formato_video":"mpeg",
            "secuencias":"344",
            "inicio_grabacion":"01/09/2015",
            "video" : {  "IDvideo": "2",
                        "inicio transmision":"01/09/2015",
                        "tamaño":"30 mb"
                        "url" :"/v2/videos/123_a/2" }
        }
        
        
## Eliminar grabacion de video de una carama [/v2/grbaciones-videos/{idvideo}]
+ parameter
    + idvideo (string) -Identificador unico de un video 

### Detener una grabacion de Video en un dispositivo de almacenamiento [DELETE]
+ response 200 (application/json)
    

        {
            "Hecho":"true"
            "message":"El video ha sido eliminado" 
         }



