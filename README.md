# ESP8266-RTOS-FONTS

This is a direct port from [extras/fonts](https://github.com/SuperHouse/esp-open-rtos/tree/master/extras/fonts) component from [esp-open-rtos](https://github.com/SuperHouse/esp-open-rtos). You can use this module along with [ESP8266-RTOS-SSD1306](https://github.com/Fonger/ESP8266-RTOS-SSD1306) to display text to oled display.

## Compatibility

[espressif/ESP8266_RTOS_SDK](https://github.com/espressif/ESP8266_RTOS_SDK) v3.2 (esp-idf style)
[ESP8266-RTOS-SSD1306](https://github.com/Fonger/ESP8266-RTOS-SSD1306)

## Usage

Clone this into your project `components` folder and run `make menuconfig` to select embeded fonts.

```c
    const font_info_t *font = font_builtin_fonts[FONT_FACE_TERMINUS_6X12_ISO8859_1];
```

## Font Definitions

```
typedef enum
{
    FONT_FACE_GLCD5x7 = 0,

    FONT_FACE_ROBOTO_8PT,
    FONT_FACE_ROBOTO_10PT,

    FONT_FACE_BITOCRA_4X7,
    FONT_FACE_BITOCRA_6X11,
    FONT_FACE_BITOCRA_7X13,

    FONT_FACE_TERMINUS_6X12_ISO8859_1,
    FONT_FACE_TERMINUS_8X14_ISO8859_1,
    FONT_FACE_TERMINUS_BOLD_8X14_ISO8859_1,
    FONT_FACE_TERMINUS_10X18_ISO8859_1,
    FONT_FACE_TERMINUS_BOLD_10X18_ISO8859_1,
    FONT_FACE_TERMINUS_11X22_ISO8859_1,
    FONT_FACE_TERMINUS_BOLD_11X22_ISO8859_1,
    FONT_FACE_TERMINUS_12X24_ISO8859_1,
    FONT_FACE_TERMINUS_BOLD_12X24_ISO8859_1,
    FONT_FACE_TERMINUS_14X28_ISO8859_1,
    FONT_FACE_TERMINUS_BOLD_14X28_ISO8859_1,
    FONT_FACE_TERMINUS_16X32_ISO8859_1,
    FONT_FACE_TERMINUS_BOLD_16X32_ISO8859_1,

    FONT_FACE_TERMINUS_6X12_KOI8_R,
    FONT_FACE_TERMINUS_8X14_KOI8_R,
    FONT_FACE_TERMINUS_BOLD_8X14_KOI8_R,
    FONT_FACE_TERMINUS_14X28_KOI8_R,
    FONT_FACE_TERMINUS_BOLD_14X28_KOI8_R,
    FONT_FACE_TERMINUS_16X32_KOI8_R,
    FONT_FACE_TERMINUS_BOLD_16X32_KOI8_R,
} font_face_t;
```

```c
typedef struct _font_info
{
    uint8_t height;                           ///< Character height in pixel, all characters have same height
    uint8_t c;                                ///< Simulation of "C" width in TrueType term, the space between adjacent characters
    char char_start;                          ///< First character
    char char_end;                            ///< Last character
    const font_char_desc_t *char_descriptors; ///< descriptor for each character
    const uint8_t *bitmap;                    ///< Character bitmap
} font_info_t;
```
