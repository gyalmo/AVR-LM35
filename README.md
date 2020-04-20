# AVR-LM35
Assuming that LM35 is connected to ADC4 channel,  a code to send converted data to port B and port D [clk/64, internal Vref and right justified]

LM35 : is an analog, linear temperature sensor whose output voltage varies linearly with change in temperature. LM35 is a three terminal linear temperature sensor from National semiconductors. It can measure temperature from-55 degree celsius to +150 degree celsius. The voltage output of the LM35 increases 10mV per degree Celsius rise in temperature. LM35 can be operated from a 5V supply and the standby current is less than 60uA.

LM35 is an analog temperature sensor. This means the output of LM35 is an analog signal. Microcontrollers don't accept analog signals as their input directly. We need to convert this analog output signal to digital before we can feed it to a microcontroller’s input. For this purpose, we can use an ADC( Analog to Digital Converter).If we are using a basic microcontroller like 8051, we need to use an external ADC to convert analog output from LM35 to digital. We then feed the output of ADC ( converted digital value) to input of 8051.  Here we  are taking the ADC 4 channel .

Assuming that LM35 is connected to ADC 4 ,

-Clk /64,

-Internal Vref and

-Right justified 
