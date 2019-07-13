# UART

## Examples

```cpp
#include <avr/io.h>

#include "LOT_uart0.h"

int main( void )
{
    uart0_init( 9600 );

    uart0_putstr( "hello world!\r\n" );

    for( ;; )
    {
        if( uart0_available() )
        {
            uart0_putchar( uart0_getchar() );
        }
    }
}
```