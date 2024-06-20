# Ultima "instant messages" patch for Atari 8bit
This patch removes delays when displaying messages. Very useful for grinding: now you don't need to spend minutes watching the same annoying messages slowly popping up.

# Patching
1) Open the "Program" disk image with a HEX editor
2) Search for following byte sequence:
F0 07 A2 C8 CA
OR use the offset: 0x000028FB
3) Replace "F0 07" with "60 EA"
4) Save the edited disk image

# This is the original code
    5804: F0 07             BEQ $580D; to be replaced with: 60 EA
    5806: A2 C8             LDX #$C8
    5808: CA                DEX
