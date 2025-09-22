# Api de meta

## Clases utilizadas al realizar las llamadas a la api

``` mermaid
classDiagram
    class RequestFacebookApi {
        +List~Datos~ Data
    }
    class Datos {
        +string event_name
        +long event_time
        +UserData user_data
        +CustomData custom_data
        +string event_source_url
        +string action_source
    }
    class UserData {
        +List~string~ Em
        +List~object~ Ph
    }
    class CustomData {
        +string Currency
        +string content_name
        +double Value
        +List~string~ content_ids
        +List~Contents~ contents
    }
    class Contents {
        +string id
        +string quantity
        +string item_price
        +string delivery_category
    }
    class OriginalEventData {
        +string EventName
        +long EventTime
    }
    class ResponseFacebook {
        +long EventsReceived
        +List~string~ Messages
        +string FbtraceId
    }
    RequestFacebookApi "1" *-- "0..*" Datos
    Datos "1" *-- "1" UserData
    Datos "1" *-- "0..1" CustomData
    CustomData "1" *-- "0..*" Contents
    ResponseFacebook o-- OriginalEventData
```

## Eventos uitlizados

**Es importante mencionar que todos los eventos necesitan un correo, por lo cual se verifica si se encuentra con sesion iniciada:**

-**Sesion iniciada:**
Se envia el correo del cliente con sesion iniciada

-**Sesion NO iniciada:**
Se envia el correo sinUsuario@trioximed.com.mx

|Evento|Situacion|
|--|--|
|ViewContentFacebookApi|Al visualizar el detalle de un producto|
|ViewContentPedidoFacebookApi|Al realizar un pedido , al regresar del checkout|
|SearchFacebookApi|Al realizar la busqueda de un producto|
|AddToCartFacebookApi|Al agregar productos al carrito|
|InitiateCheckoutFacebookApi|Al comenzar el checkout (aun no se realiza ningun pago)|
|PurchaseFacebookApi|Al realizar el pago en el checkout|
