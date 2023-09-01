# TallerFinalizado
Taller
//
import java.util.*;
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.time.temporal.ChronoUnit;
import java.util.Arrays;
import java.util.List;

public class Main {
  record InformacionPersonal(String nombres, 
                               String apellidos,
                               LocalDate fechaDeNacimiento, 
                               String direccion, 
                               String municipio,
                               String nivelAcademico,
                               String ocupacion, 
                               Character genero, 
                               Integer peso, 
                               Double estatura){}
    public static void main(String[] args) {
      List<InformacionPersonal> data = new ArrayList<>();
  	data.add ( new InformacionPersonal ("Juan",
                                                   "Perez",
                                                   LocalDate.parse("15/03/1985", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                   "Calle 123",
                                                   "Medellin",
                                                   "Licenciatura en Ingenieria",
                                                   "Ingeniero de Software",
                                                   'M',
                                                   70,
                                                   1.75d));
		data.add (new InformacionPersonal ("Maria",
                                                   "Garcia",
                                                   LocalDate.parse("28/07/1992", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                   "Calle 123",
                                                   "Medellin",
                                                   "Maestria en Psicologia",
                                                   "Psicologa Clinica",
                                                   'F',
                                                   58,
                                                   1.68d));
		data.add (new InformacionPersonal ("Carlos",
                                                    "Perez Garcia", 
                                                    LocalDate.parse("10/03/2023", DateTimeFormatter.ofPattern("dd/MM/uuuu")), 
                                                    "Calle 123", 
                                                    "Medellin",
                                                    "",
                                                    "",
                                                    'M', 
                                                    30, 
                                                    0.80d));
		data.add (new InformacionPersonal ("Ana",
                                                    "Martinez", 
                                                    LocalDate.parse("05/09/2009", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Calle 14",
                                                    "Villa", 
                                                    "Bachiller", 
                                                    "Estudiante", 
                                                    'F',
                                                    55, 
                                                    1.60d));
		data.add (new InformacionPersonal ("Luisa", 
                                                    "Hernandez",
                                                    LocalDate.parse("20/06/1989", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Carrera 789", 
                                                    "Envigado", 
                                                    "Doctorado en Economia", 
                                                    "Profesora Universitaria", 
                                                    'F', 
                                                    63, 
                                                    1.70d));
		data.add (new InformacionPersonal ("Javier", 
                                                    "Lopez", 
                                                    LocalDate.parse("12/04/1975", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Calle San Juan", 
                                                    "Medellin", 
                                                    "Licenciatura en Arquitectura", 
                                                    "Arquitecto Independiente", 
                                                    'M', 
                                                    75, 
                                                    1.82d));
		data.add (new InformacionPersonal ("Laura", 
                                                    "Ramirez", 
                                                    LocalDate.parse("18/04/1998", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Avenida 6", 
                                                    "Ciudad Metropolitana", 
                                                    "Bachiller", 
                                                    "Estudiante", 
                                                    'F', 
                                                    52, 
                                                    1.65d));
		data.add (new InformacionPersonal ("Martin", 
                                                    "Torres", 
                                                    LocalDate.parse("30/02/1998", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Avenida 6", 
                                                    "Aldea", 
                                                    "Bachiller", 
                                                    "Estudiante", 
                                                    'M', 
                                                    68, 
                                                    1.78d));
		data.add (new InformacionPersonal ("Sofia", 
                                                    "Vargas", 
                                                    LocalDate.parse("22/07/1995", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Avenida 6", 
                                                    "Rionegro", 
                                                    "Bachiller", 
                                                    "Estudiante", 
                                                    'F', 
                                                    60, 
                                                    1.63d));
		data.add (new InformacionPersonal ("Daniel",
                                                    "Sanchez",
                                                    LocalDate.parse("08/12/1999", DateTimeFormatter.ofPattern("dd/MM/uuuu")),
                                                    "Avenida 6",
                                                    "Rionegro",
                                                    "Bachiller",
                                                    "Estudiante",
                                                    'M',
                                                    72,
                                                    1.79d));
                                                    
    //Direcciones                                                
    System.out.println("Las direcciones de cada persona son: ");
		for ( InformacionPersonal informacionPersonal : data ) {
			System.out.println(informacionPersonal.direccion);
		}
                System.out.println();
    //Peso
                System.out.println("El peso de cada persona es: ");
                int k=0, j=0;
		for ( InformacionPersonal informacionPersonal : data ) {
                        System.out.println(informacionPersonal.peso);
                        k=k + informacionPersonal.peso;
                }
                j=(k/10);
                System.out.println("La media de los pesos es: "+j);
                System.out.println();
    //Estatura
                System.out.println("La estatura de cada persona es: ");
                Double menorEstatura=Double.MAX_VALUE;
                Double mayorEstatura=0d;
		for ( InformacionPersonal informacionPersonal : data ) {
                        System.out.println(informacionPersonal.estatura);
                        if (informacionPersonal.estatura<menorEstatura){
                            menorEstatura = informacionPersonal.estatura;
                        }
                        if (informacionPersonal.estatura>mayorEstatura){
                            mayorEstatura = informacionPersonal.estatura;
                        }
                }
                System.out.println("La menor estatura de las personas es: " + menorEstatura);
                System.out.println("La mayor estatura de las personas es: " + mayorEstatura);
                System.out.println();
    //Genero
                int i=0, x=0;
		for ( InformacionPersonal informacionPersonal : data ) {
                        if(informacionPersonal.genero == 'M'){
                            i++;
                        }else {
                        x++;
                        }
                }
                System.out.println("El total de personas Masculinas es: " + i);
                System.out.println("El total de personas Femeninas es: " + x);
                System.out.println();
    //Nombre completo
                System.out.println("Los nombres completos de todas las personas son: ");
		for ( InformacionPersonal informacionPersonal : data ) {
			System.out.println(informacionPersonal.nombres + " " + informacionPersonal.apellidos + ".");
		}
                System.out.println();
    //Edades 
                System.out.println("Las edades de cada persona son: ");
                int valorMinimo=Integer.MAX_VALUE;
		for ( InformacionPersonal informacionPersonal : data ) {
                    long aniosDiferencia = ChronoUnit.YEARS.between( informacionPersonal.fechaDeNacimiento, LocalDate.now());
                    System.out.println(aniosDiferencia);
                    if (((int)aniosDiferencia) < valorMinimo){
                       valorMinimo = ((int)aniosDiferencia);
                    }
		}
                    System.out.println("La edad menor es: "+ valorMinimo);
  }
}
