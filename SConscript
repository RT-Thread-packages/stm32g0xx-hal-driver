from building import *
import os

cwd = GetCurrentDir()
path = [os.path.join(cwd, 'Inc')]
src_path = os.path.join(cwd, 'Src')

CPPDEFINES = ['USE_HAL_DRIVER']

src = [
os.path.join(src_path, 'stm32g0xx_hal_cec.c'),
os.path.join(src_path, 'stm32g0xx_hal_rcc.c'),
os.path.join(src_path, 'stm32g0xx_hal_rcc_ex.c'),
os.path.join(src_path, 'stm32g0xx_hal_flash.c'),
os.path.join(src_path, 'stm32g0xx_hal_flash_ex.c'),
os.path.join(src_path, 'stm32g0xx_hal_dma.c'),
os.path.join(src_path, 'stm32g0xx_hal_dma_ex.c'),
os.path.join(src_path, 'stm32g0xx_hal_pwr.c'),
os.path.join(src_path, 'stm32g0xx_hal_pwr_ex.c'),
os.path.join(src_path, 'stm32g0xx_hal_cortex.c'),
os.path.join(src_path, 'stm32g0xx_hal.c'),
os.path.join(src_path, 'stm32g0xx_hal_gpio.c'),
]

if GetDepend(['RT_USING_SERIAL']) or GetDepend(['RT_USING_NANO', 'RT_USING_CONSOLE']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_uart.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_uart_ex.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_usart_ex.c')]
    src += [os.path.join(src_path, 'stm32g0xx_ll_usart.c')]

if GetDepend(['RT_USING_I2C']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_i2c.c')]
    src += [os.path.join(src_path, 'stm32g0xx_ll_i2c.c')]


if GetDepend(['RT_USING_SPI']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_spi.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_spi_ex.c')]
    src += [os.path.join(src_path, 'stm32g0xx_ll_spi.c')]

if GetDepend(['RT_USING_HWTIMER']) or GetDepend(['RT_USING_PWM']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_tim.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_tim_ex.c')]
    src += [os.path.join(src_path, 'stm32g0xx_ll_tim.c')]

if GetDepend(['RT_USING_ADC']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_adc.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_adc_ex.c')]
    src += [os.path.join(src_path, 'stm32g0xx_ll_adc.c')]

if GetDepend(['RT_USING_WDT']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_iwdg.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_wwdg.c')]

if GetDepend(['RT_USING_RTC']):
    src += [os.path.join(src_path, 'stm32g0xx_hal_rtc.c')]
    src += [os.path.join(src_path, 'stm32g0xx_hal_rtc_ex.c')]
    src += [os.path.join(src_path, 'stm32g0xx_ll_rtc.c')]



group = DefineGroup('STM32G0-HAL', src, depend = ['PKG_USING_STM32G0_HAL_DRIVER'], CPPPATH = path, CPPDEFINES = CPPDEFINES)

Return('group')
