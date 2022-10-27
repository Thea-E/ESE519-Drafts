# ESE519-Drafts

## Lab 2B - Oct.21
### LED controlled with keyboard input
C codes:
```
#include <stdio.h>
#include "pico/stdlib.h"
#define PICO_A0 29

int main() {
    stdio_init_all();
    gpio_init(PICO_A0);
    gpio_set_dir(PICO_A0, true);
    //gpio_put(PICO_A0, true);

    uint input;
    while (true) {
        
        scanf("%d", &input);

        if(input == 1){
            gpio_put(PICO_A0, true);
        }
        else{
            gpio_put(PICO_A0, false);
        }
        printf("Current input is: %d", input);
        printf("\n");
        sleep_ms(1000);
    }

    return 0;
}
```
https://github.com/Thea-E/ESE519-Drafts/blob/main/ezgif.com-gif-maker.gif

## Lab 2B - Oct.27
### Goal
We want to prototype a light sensing system with PY2040 and ADPS9960. 
*  When ADPS senses the bright light, we will turn on the red LED (connected to 2040 via GPIO pin A0), and turn it off after several ms. 
*  When ADPS senses the dim light, we will turn on the yellow LED (connected to 2040 via GPIO pin A2), and turn it off after several ms. 

### Protoboard
We hand-soldered the board with female headers on the proto-breadboard, and we also soldered two extra female headers(the outside bigger ones in the picture) to provide access for extra pins connections.
<img width="800" alt="sm in out" src="https://user-images.githubusercontent.com/84453030/198374783-e76f4a16-ba5a-4ac7-b130-23c7f5e5c90d.jpeg">


Meanwhile, we use the breadboard to test our plan. Check this gif to see the result https://github.com/Thea-E/ESE519-Drafts/blob/main/breadboard.gif .
Here's the pin match diagram.

| Pin  | Usage |
| ------------- | ------------- |
| GND  | Ground  |
| A0  | GPIO, set as 0 or 1(3V) to power the LED  |
| A2  | GPIO, set as 0 or 1(3V) to power the LED  |


Next, when we finished the soldering, we re-test it on our protoboard, and it worked perfectly! Check the gif there to see the result https://github.com/Thea-E/ESE519-Drafts/blob/main/prototype.gif .


