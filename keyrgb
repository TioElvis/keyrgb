#!/bin/bash

MODEL="GS65"
CMD="msi-perkeyrgb --model $MODEL"

case "$1" in
    disable)
        $CMD -d
        ;;
    # === COLORES ===
    red)
        $CMD -s ff9500
        ;;
    green)
        $CMD -s 00ffaa
        ;;
    blue)
        $CMD -s 0000ff
        ;;
    yellow)
        $CMD -s ffff00
        ;;
    cyan)
        $CMD -s 00ffff
        ;;
    magenta|purple)
        $CMD -s ff00ff
        ;;
    white)
        $CMD -s ffffff
        ;;
    orange)
        $CMD -s ff8800
        ;;
    # === PRESETS ===
    aqua|chakra|default|disco|drain|freeway|rainbow-split|roulette)
        $CMD -p "$1"
        ;;
    # === OPCIONES AVANZADAS ===
    -s|--color)
        if [[ -z "$2" ]]; then
            echo "Error: missing color. Usage: keyrgb --color <HEX>" >&2
            exit 1
        fi
        $CMD -s "$2"
        ;;
    -p|--preset)
        if [[ -z "$2" ]]; then
            echo "Error: missing preset. Usage: keyrgb --preset <NAME>" >&2
            exit 1
        fi
        $CMD -p "$2"
        ;;
    -c|--config)
        if [[ -z "$2" ]]; then
            echo "Error: missing file. Usage: keyrgb --config <FILE>" >&2
            exit 1
        fi
        $CMD -c "$2"
        ;;
    ""|--help|-h)
        echo "Usage: keyrgb <option>"
        echo ""
        echo "Quick commands:"
        echo "  disable"
        echo ""
        echo "Colors:"
        echo "  red             Orange-red color  (#ff9500)"
        echo "  green           Mint green color  (#00ffaa)"
        echo "  blue            Blue color        (#0000ff)"
        echo "  yellow          Yellow color      (#ffff00)"
        echo "  cyan            Cyan color        (#00ffff)"
        echo "  magenta         Magenta color     (#ff00ff)"
        echo "  orange          Orange color      (#ff8800)"
        echo "  white           White color       (#ffffff)"
        echo ""
        echo "Presets:"
        echo "  aqua, chakra, default, disco,"
        echo "  drain, freeway, rainbow-split, roulette"
        echo ""
        echo "Options:"
        echo "  -s, --color  <HEX>    Custom color (e.g. ff0000)"
        echo "  -p, --preset <NAME>   System preset"
        echo "  -c, --config <FILE>   Per-key configuration file"
        echo "  -h, --help            Show this help message"
        ;;
    *)
        echo "Error: unknown option '$1'." >&2
        echo "Run 'keyrgb --help' to see available options." >&2
        exit 1
        ;;
esac
