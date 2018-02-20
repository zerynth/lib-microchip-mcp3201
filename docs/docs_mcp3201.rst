****************
 MCP3201 Module
****************

This module contains the driver for Microchip MCP3201 analog to digital converter with
SPI serial interface (`datasheet <http://ww1.microchip.com/downloads/en/DeviceDoc/21290F.pdf>`_).

Example: ::
        
        from microchip.mcp3201 import mcp3201
        
        ...
        
        mcp = mcp3201.MCP3201(SPI0, D17)
        value = mcp.get_raw_data()
    
    
===============
 MCP3201 class
===============


.. class:: MCP3201(spidrv, cs, clk = 400000)

    Creates an instance of the MCP3201 class.
    
    :param spidrv: SPI Bus used '(SPI0, ...)'
    :param cs: Chip select pin
    :param clck: Clock speed, default 400 kHz
    
    
    
.. method:: get_raw_data()
    
    Return the conversion result as an integer between 0 and 4095 (12 bit).
    The digital output code is determined by the reference voltage *Vref* and the analog input voltage *Vin*:
    
    Digital output code = 4096 * *Vin* / *Vref*
    
    
