[rough register descriptions](https://github.com/fifteenhex/linux-ssc325/blob/v4.9.84-sigmastar/drivers/sstar/crypto/hal/infinity3/halAESDMA.h)

### RNG

RNG block registermap:

| Offset | Name   | Comment |
|--------|--------| ---     |
| 0x00   | CTRL   | bit7 - enable/initialize? |
| 0x08   | VALUE  | The output value. Ready when STATUS[0] is 1 |
| 0x0C   | STATUS | bit0 - ready |

### SHA

SHA block registermap:

| Offset    | Name       | 15 | 14          | 13             | 12 | 11 | 10 | 9         | 8 | 7 | 6        | 5 | 4 | 3 | 2     | 1              | 0 | Comment                                                                          |
|-----------|------------|----|-------------|----------------|----|----|----|-----------|---|---|----------|---|---|---|-------|----------------|---|----------------------------------------------------------------------------------|
| 0x20      | CTRL       |    | CTRL_MANUAL | CTRL_INIT_HASH |    |    |    | CTRL_MODE |   |   | CTRL_CLR |   |   |   |       | CTRL_FIRE_ONCE |   | write 1 to fire once,  0 = SHA-1  1 = SHA-256  enable/disable initial hash value |
| 0x28      | BUF_ADDR_L |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   |                                                                                  |
| 0x2C      | BUF_ADDR_H |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   |                                                                                  |
| 0x30      | BUF_LEN_L  |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   |                                                                                  |
| 0x34      | BUF_LEN_H  |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   |                                                                                  |
| 0x38      | BUF_ADDR_L |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   |                                                                                  |
| 0x3C      | STATUS     |    |             |                |    |    |    |           |   |   |          |   |   |   | BUSY? |                |   | bit 0 = ready, bit 1 - busy ?                                                    |
| 0x40-0x5f | VALUE      |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   | When reading - the output value, when writing - initial hash value (big endian)  |
| 0xB8      | WORD_CNT_L |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   | count in 4-byte words, lower 16 bits                                             |
| 0xBC      | WORD_CNT_H |    |             |                |    |    |    |           |   |   |          |   |   |   |       |                |   | higher 16 bits                                                                   |

### RSA

### AESDMA

| Offset | Name | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 | Comment |
|--------|------|----|----|----|----|----|----|---|---|---|---|---|---|---|---|---|---|---------|
| 0x140  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x144  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x148  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x14c  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x150  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x154  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x158  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x15c  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x160  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x164  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |
| 0x1e4  |      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |   |   |         |

On infinity3 the base address is 0x1f224400