<h1 style="color:red;"> Ciudad Mitad del Mundo </h1>
<img src="https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.howlanders.com%2Fblog%2Fecuador%2Fciudad-mitad-mundo-quito%2F&psig=AOvVaw2cOSlq8GVmZJ2MBdBpd59T&ust=1676586428929000&source=images&cd=vfe&ved=0CBAQjRxqFwoTCMicpKbJmP0CFQAAAAAdAAAAABAE.jpg"
     alt="Monumento a la expedición Francesa" width="400" height="453" />

<body>

    <h1>Calculadora de Distancia a la Mitad del Mundo</h1>

    <p>Su ubicación actual: <span id="location"></span></p>

    <p>Distancia a la mitad del mundo: <span id="distance"></span></p>



    <script>

      // Obtener la ubicación actual

      navigator.geolocation.getCurrentPosition(function (position) {

        var lat1 = position.coords.latitude;

        var lon1 = position.coords.longitude;



        // La ubicación de Quito es  ??

        var lat2 = -0.0102496 ;

        var lon2 = -78.4464668;



        // Función para calcular la distancia en kilómetros

        var R = 6371; // Radio de la Tierra (km)

        var dLat = (lat2 - lat1) * (Math.PI / 180);

        var dLon = (lon2 - lon1) * (Math.PI / 180);

        var a = Math.sin(dLat / 2) * Math.sin(dLat / 2) +

                Math.cos(lat1 * (Math.PI / 180)) * Math.cos(lat2 * (Math.PI / 180)) *

                Math.sin(dLon / 2) * Math.sin(dLon / 2);

        var c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));

        var d = R * c;



        // Mostrar la distancia en la página

        document.getElementById("location").innerHTML = lat1 + ", " + lon1;

        document.getElementById("distance").innerHTML = d + " km";

      });

    </script>

  </body>
