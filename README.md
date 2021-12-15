# Orchid Tiny Turbo 286 Accelerator Card
This was an accelerator card available in the 1980s, and it was designed to upgrade IBM PCs and XTs from a 4.77MHz 8088 up to an 8MHz 80286.

During my [troubleshooting efforts](https://twitter.com/TubeTimeUS/status/1467203559154323459) I ended up completely reverse engineering the card, so here is the schematic!

[Schematic PDF](https://github.com/schlae/tiny-turbo-286/blob/main/TinyTurbo286Sch.pdf)

This schematic is from the 1986 revision B of the card.

## Notes

**The PALs have not yet been reverse engineered, so this information is incomplete and you can't build a card from this.**

The card includes an onboard 8KB cache. Each location in the cache has an 8-bit tag which encodes the top 7 memory addresses. The lower address bits get mapped 1:1 to the cache address bits. This means that the cache doesn't work well when the CPU has to frequently fetch data from the same location in different 8KB pages of main memory.

There is a daughterboard that plugs into the 0.1" header J1. The daughtercard is designed as a passthrough and contains a header for a cable that plugs into the motherboard's 8088 socket. The daughtercard also contains a socket for an 8088. This is for the non-turbo mode (selected by flipping the card's toggle switch into the down position.) In turbo mode, the daughtercard's reset line is asserted and all of the 8088's pins float.

Jumper W1 is designed to be closed when the card is plugged into an IBM XT's slot 8.

