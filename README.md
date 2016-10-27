
//Inicializar variables de pines

int sw_1=7; 
int sw_2=6; 
int lim=0;
int vector_leds [6]={8,9,10,11,12,13};
//
int i;
int j;
int cont;
int cont_1;

//
void setup() {
 
  pinMode(8,OUTPUT); 
  pinMode(9,OUTPUT); 
  pinMode(10,OUTPUT); 
  pinMode(11,OUTPUT); 
  pinMode(12,OUTPUT); 
  pinMode(13,OUTPUT); 
  pinMode(sw_1,INPUT); 
  pinMode(sw_2,INPUT); 

}

void loop() {

  
  //Juego de luces 1 For Anidado
  
    if(digitalRead(sw_1)==HIGH&&digitalRead(sw_2)==LOW){
           delay(200);
           
           for(j=0;j<5;j++){//for 1
              for(i=8;i<14;i++){//for 2
                       digitalWrite(i,HIGH);
                       delay(100);
               }//For 2
               for(i=13;i>7;i--){//for 3
                      digitalWrite(i,LOW);
                      delay(100);
                 }//for 3
               i=8;
              }//for 1    
              delay(300);//Tiempo  antes de empzar el proximo juego  
              i=0;
            }  
            
//
    //juego randomico
      
         if(digitalRead(sw_2)==LOW&&digitalRead(sw_1)==HIGH){
              delay(200);
             lim=random(5);
              for(j=0;j<lim;j++){//For 1
                 for (cont = 8,cont_1=13; cont < 11; cont++,cont_1--) { //For 2
                    digitalWrite(cont, HIGH);
                    digitalWrite(cont_1, HIGH);
                    delay(150);
                   }//For 2

                 for (cont = 10, cont_1=11; cont_1 < 14; cont--,cont_1++) {//For 3
                     digitalWrite(cont, LOW);
                     digitalWrite(cont_1, LOW);
                     delay(150);
                    }//For 3
                 }//For 1
       }
        delay(300);
      }
     
