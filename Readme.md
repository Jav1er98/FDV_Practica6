## Práctica 6: Actividad Sprites.
## Objetivo: Manejo y edición de Sprites en un juego 2D que proporciona Unity.

1. Importar los assets de Zombie y Goblin.
      
2. Crear un script para controlar el movimiento para el personaje Zombie. Hacer una versión sin salto y otra con salto, para lo cual es mejor que sea un objeto físico y añadimos una fuerza. Creamos un objeto para presentar el personaje. En este caso sólo tendremos que mover las coordenadas (X, Y). Tendremos que usar además las clases Rigidbody2D y Vector2 o Transform y Vector3. Además necesitamos que el sprite se oriente hacia donde camina, usando la propiedad Flip en el eje X en función de si se está moviendo hacia la izquierda (movimiento negativo) o hacia la derecha (movimiento positivo). El suelo se considera en la y = 0

      - Sin salto. En esta caso para llevar a cabo el movimiento del Zombie añado un Rigidbody al personaje y un Box Collider ambos 2D, junto con un objeto vacio que llamaré GroundCheck, que lo colocó justo en los pies del personaje y podamos hacer una comprobación de cuando está tocando el suelo donde camina, además de añadiler la propiedad Flip que la hago entorno al eje X, para que gire en la dirreción que le corresponda.
      
      ![gif ejercicio 1](/gifs/Ejercicio8.gif)
      
      - Con salto. Añadimos un AddForce y un proviedad booleana para el salto, también le añadí, sus correspondientes animaciones, cuando está en el estado Idle o Walking.
      
      ![gif ejercicio 2](/gifs/Ejercicio9.gif)

3. Agregar un sprite zombie, con un collider2D, y crear un script, en el que el zombie, al colisionar con él cambie la animación a Dead.
       
      - Añadimos al script del zombie un OnCollisionEnter2D, para que en el momento que toque al globin se active la animación Dead, que configuramos en el Animator del zombie.
      
      ![gif ejercicio 3](/gifs/Ejercicio10.gif)
       
4. Crear las animaciones de Goblin. Añadir un script al zombie, para que al colisionar con Goblin, Goblin active la animación de atacar.

      - Creamos un script al goblin con un OnCollisionEnter2D , para que en el momento que lo toque el zombie active la animación de Atacar, que configuramos en el Animator del Goblin.
      
      ![gif ejercicio 4](/gifs/Ejercicio11.gif)
      
5. Añadir un elemento decorativo, que permita crear un Joint a uno de los personajes.

      - Introducimos un círculo  que contenía un componente RigidBody en el escenario y se agregó un componente SpringJoint2D al Zombie, lo que hace que el zombie gire entorno al círculo y no pueda avanzar.
      
      ![gif ejercicio 5](/gifs/Ejercicio12.gif)
      
6. Pruebas de física 2D:
     
     1. Ninguno de los objetos será físico.
     
      - Se mantienen en sus posiciones iniciales.
    
      ![gif ejercicio 6](/gifs/Ejercicio1.gif)
       
      2. Un objeto tiene físicas y el otro no.
      
      - El Goblin no tiene fisicas y el zombie si, en esta caso el zombie puede moverse.
      
      ![gif ejercicio 6](/gifs/Ejercicio2.gif)
       
      3. Ambos objetos tienen físicas.
      
      - El zombie empuja al goblin a una gran distancia.
      
      ![gif ejercicio 6](/gifs/Ejercicio3.gif)
      
      4. Ambos objetos tienen físcas y uno de ellos tiene 10 veces más masa que el otro.
      
      - El  goblin tiene 10 veces más de masa y apenas lo empuja.
       
      ![gif ejercicio 6](/gifs/Ejercicio4.gif)
      
      5. Un objeto tiene físicas y el otro es IsTrigger.
      
      - El zombie se solapa con el goblin.
      
      ![gif ejercicio 6](/gifs/Ejercicio5.gif)
      
      6. Ambos objetos son físicos y uno de ellos está marcado como IsTrigger.
      
      - El goblin al estar con fisicas y marcado como IsTrigger cae indefinidamente.
       
      ![gif ejercicio 6](/gifs/Ejercicio6.gif)
      
      7. Uno de los objetos es cinemático.
      
      - El goblin actua como un muro, y no está sujeto a las físicas del motor.
      
      ![gif ejercicio 6](/gifs/Ejercicio7.gif)
      
