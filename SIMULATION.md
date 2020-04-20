#include <avr/io.h>

int main(void)
{
    DDRB=0xFF;                                                                                  //PORT B AS OUTPUT
    DDRD=0xFF;                                                                                  //PORT D AS OUTPUT
    DDRA&=~(1<<PINA4);                                                                          //SETTING PORTA PIN 4 AS INPUT
    ADCSRA|=(1<<ADEN)|(1<<ADPS2)|(1<<ADPS1);                                                    //SETTING ADPS2,ADPS1,ADPS0 COMBINATION AS | 1 | 1| 0| IN  REGISTER ADCSRA FOR PRESCALAR CLK/64
    ADMUX|=(1<<REFS1)|(1<<REFS0);                                                               //FOR SELECTING REFERENCE VOLTAGE
    ADMUX&=~(1<<ADLAR);                                                                         //RIGHT JUSTIFIED
    ADMUX|=(1<<MUX4);                                                                           //ENABLE CHANNEL 4 OF ADC
    
    while(1)
    {
        ADCSRA|=(1<<ADSC);                                                                      //START CONVERSION
        while(!(ADCSRA&(1<<ADIF)));                                                             //WAIT TILL CONVERSION IS COMPLETE AND ADIF FLAG IS 1
        PORTB=ADCL;                                                                             //LOWER
        PORTD=ADCH;                                                                             //HIGHER
    }
} 
