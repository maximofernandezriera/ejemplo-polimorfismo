# Un poco de polimorfismo

Se trata de comportamientos diferentes, asociados a objetos distintos. Lo interesante es que al llamarlos se utilizará el comportamiento correspondiente al objeto que se esté usando.

# Un ejemplo sencillo de polimorfismo en Java

Vamos a aplicar lo visto en la teoría. Implementaremos una clase Vehiculo que tiene un método mover() que es sobreescrito por las clases Coche y Bicicleta. Luego, en el método main, se creará una instancia de la clase Coche y se asigna a una variable de tipo Vehiculo. Eso es exactamente el polimorfismo.

Cuando se llama al método mover() en esa variable, se ejecuta el método sobreescrito en la clase Coche. Lo mismo sucede cuando se asigna una instancia de la clase Bicicleta a la misma variable y se llama al método mover().

# Implementación

            class Vehiculo {
                public void mover(int distancia) {
                    System.out.println("El vehículo se está moviendo " + distancia + " metros");
                }
            }

            class Coche extends Vehiculo {
                public void mover(int distancia) {
                    System.out.println("El coche está avanzando " + distancia + " metros");
                    if (distancia > 10) {
                        System.out.println("El coche está yendo rápido");
                    } else {
                        System.out.println("El coche está yendo lento");
                    }
                }
            }

            class Bicicleta extends Vehiculo {
                public void mover(int distancia) {
                    System.out.println("La bicicleta está pedaleando " + distancia + " metros");
                    if (distancia > 5) {
                        System.out.println("La bicicleta está yendo rápido");
                    } else {
                        System.out.println("La bicicleta está yendo lento");
                    }
                }
            }

            public class PolimorfismoEjemplo {
                public static void main(String[] args) {
                    Vehiculo miVehiculo = new Coche();
                    miVehiculo.mover(15); // El coche está avanzando 15 metros
                                         // El coche está yendo rápido
                    miVehiculo = new Bicicleta();
                    miVehiculo.mover(3); // La bicicleta está pedaleando 3 metros
                                         // La bicicleta está yendo lento
                }
            }
            
# Un reto, basado en este ejemplo, para resolver en unos minutos

Implementa una clase Animal con un método hacerSonido(int veces) que tome un parámetro veces e imprima un mensaje genérico como “El animal está haciendo un sonido” el número de veces indicado por el parámetro. Luego, crea dos clases que extiendan de Animal: Perro y Gato. En ambas clases, sobrescribe el método hacerSonido(int veces) para imprimir un mensaje específico para cada animal (por ejemplo, “El perro está ladrando” y “El gato está maullando”) el número de veces indicado por el parámetro. Finalmente, en el método main, crea una instancia de la clase Perro y otra de la clase Gato, y llama al método hacerSonido(int veces) en ambas instancias con diferentes valores para el parámetro.

# NO MIRÉIS LA SOLUCIÓN

# Solución

Primero, creamos la clase Animal con el método hacerSonido(int veces):

        class Animal {
            public void hacerSonido(int veces) {
                for (int i = 0; i < veces; i++) {
                    System.out.println("El animal está haciendo un sonido");
                }
            }
        }

Luego, creamos las clases Perro y Gato que extienden de la clase Animal. En ambas clases sobrescribimos el método hacerSonido(int veces) para imprimir un mensaje específico para cada animal el número de veces indicado por el parámetro:

          class Perro extends Animal {
              public void hacerSonido(int veces) {
                  for (int i = 0; i < veces; i++) {
                      System.out.println("El perro está ladrando");
                  }
              }
          }

          class Gato extends Animal {
              public void hacerSonido(int veces) {
                  for (int i = 0; i < veces; i++) {
                      System.out.println("El gato está maullando");
                  }
              }
          }

Finalmente, en el método main creamos una instancia de la clase Perro y otra de la clase Gato, y llamamos al método hacerSonido(int veces) en ambas instancias con diferentes valores para el parámetro:

          public class PolimorfismoEjercicio {
              public static void main(String[] args) {
                  Animal miAnimal = new Perro();
                  miAnimal.hacerSonido(3); // El perro está ladrando
                                           // El perro está ladrando
                                           // El perro está ladrando
                  miAnimal = new Gato();
                  miAnimal.hacerSonido(2); // El gato está maullando
                                           // El gato está maullando
              }
          }
