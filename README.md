# emu8080
u/PM_ME_YOUR_EMULATORS' Intel 8080 emulator

# original post: www.reddit.com/r/EmuDev/comments/af4mhe/

Sharing my Intel 8080 emulator for anyone who might find it useful
Like the title says, just sharing my 8080/8085 emulator written a few months back. I used it in a microcontroller-based Space Invaders emulator. It's C code. Compiles on anything. I even compiled it in real-mode DOS! :)

The only functions that you'll want to call externally are:

**void i8080_reset()** - Call this before execution or when you want to hard-reset.

**void i8080_interrupt(uint8_t n)** - Trigger a hardware interrupt, where _n_ is the interrupt number.

**int i8080_exec(int cycles)** - Execute cycles number of cycles. Return value is the (negative) number of cycles executed beyond what was requested. (add return value to your next i8080_exec call if your emulated system is timing-critical)

See the prototyped functions at the beginning of the code to see what external functions you need to provide for it. There are only four.

I tried to keep it very easy to read, so it could be useful for an emulation beginner that's still trying to learn.

It's cycle-accurate, and it passes every test suite I've found. I haven't tested the 8085 extensions, but it _should_ work, based on the documentation that I've read.

Source code: https://pastebin.com/VSf7GUne

Have fun!
