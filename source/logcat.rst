Android trunk Emulatorで起動したログをそのまま出力
===============================================================================

dalvik -Xjitverbose
adb logcat

log sample ::

  D/dalvikvm(  149): JIT started for system_server
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for fixSlashes, offset 0xb
  D/dalvikvm(  149): 0x45c968ae: 0x0049 aget-char v0, v6, v1
  D/dalvikvm(  149): 0x45c968b2: 0x0013 const/16 v7, (#47), (#0)
  D/dalvikvm(  149): 0x45c968b6: 0x0033 if-ne v0, v7, (+f)
  D/dalvikvm(  149): TRACEINFO (1): 0x45c96898 Ljava/io/File;fixSlashes.(Ljava/lang/String;)Ljava/lang/String; 0xb 6 of 56, 6 blocks
  D/dalvikvm(  149): Compiling Ljava/io/File; fixSlashes
  D/dalvikvm(  149): 56 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 000b - 000b empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (000b)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 000b - 000f)
  D/dalvikvm(  149):   Taken branch: block 3 (001e)
  D/dalvikvm(  149):   Fallthrough : block 2 (0011)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 0011 - 0011 empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 001e - 001e empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45c968ae
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487000
  D/dalvikvm(  149): total size is 116 bytes
  D/dalvikvm(  149): 0x4d487000 (0000): data    0xc028(49192)
  D/dalvikvm(  149): 0x4d487002 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487004 (0004): data    0x0054(84)
  D/dalvikvm(  149): 0x4d487006 (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48700a (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d48700c (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d48700e (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x000b
  D/dalvikvm(  149): L0x4ac2a110:
  D/dalvikvm(  149): -------- dalvik offset: 0x000b @ aget-char v0, v6, v1
  D/dalvikvm(  149): 0x4d487010 (0010): ldr     r0, [r5, #24]
  D/dalvikvm(  149): 0x4d487012 (0012): ldr     r1, [r5, #4]
  D/dalvikvm(  149): 0x4d487014 (0014): cbz     r0,0x4d487036 (L0x4ac2a5b0)
  D/dalvikvm(  149): 0x4d487016 (0016): ldr     r3, [r0, #8]
  D/dalvikvm(  149): 0x4d487018 (0018): add     r2,r0,#16
  D/dalvikvm(  149): 0x4d48701c (001c): cmp     r1, r3
  D/dalvikvm(  149): 0x4d48701e (001e): bcs     0x4d487036 (L0x4ac2a5b0)
  D/dalvikvm(  149): 0x4d487022 (0022): ldrh    r4, [r2, r1, LSL #1]
  D/dalvikvm(  149): -------- dalvik offset: 0x000d @ const/16 v7, (#47), (#0)
  D/dalvikvm(  149): 0x4d487026 (0026): movs    r7, #47
  D/dalvikvm(  149): -------- dalvik offset: 0x000f @ if-ne v0, v7, (+f)
  D/dalvikvm(  149): 0x4d487028 (0028): cmp     r4, r7
  D/dalvikvm(  149): 0x4d48702a (002a): str     r7, [r5, #28]
  D/dalvikvm(  149): 0x4d48702c (002c): str     r4, [r5, #0]
  D/dalvikvm(  149): 0x4d48702e (002e): bne     0x4d48704c (L0x4ac2a190)
  D/dalvikvm(  149): 0x4d487032 (0032): b       0x4d487040 (L0x4ac2a150)
  D/dalvikvm(  149): 0x4d487034 (0034): undefined
  D/dalvikvm(  149): L0x4ac2a5b0:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45c968ae @ +0x000b
  D/dalvikvm(  149): 0x4d487036 (0036): ldr     r0, [r15pc, #56]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d48703a (003a): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d48703c (003c): blx     r1
  D/dalvikvm(  149): 0x4d48703e (003e): .align4
  D/dalvikvm(  149): L0x4ac2a150:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0011
  D/dalvikvm(  149): 0x4d487040 (0040): b       0x4d487044 (L0x4ac2ad44)
  D/dalvikvm(  149): 0x4d487042 (0042): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2ad44:
  D/dalvikvm(  149): 0x4d487044 (0044): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487046 (0046): blx     r0
  D/dalvikvm(  149): 0x4d487048 (0048): data    0x68ba(26810)
  D/dalvikvm(  149): 0x4d48704a (004a): data    0x45c9(17865)
  D/dalvikvm(  149): 0x4d48704c (004c): .align4
  D/dalvikvm(  149): L0x4ac2a190:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x001e
  D/dalvikvm(  149): 0x4d48704c (004c): b       0x4d487050 (L0x4ac2af44)
  D/dalvikvm(  149): 0x4d48704e (004e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2af44:
  D/dalvikvm(  149): 0x4d487050 (0050): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487052 (0052): blx     r0
  D/dalvikvm(  149): 0x4d487054 (0054): data    0x68d4(26836)
  D/dalvikvm(  149): 0x4d487056 (0056): data    0x45c9(17865)
  D/dalvikvm(  149): -------- end of chaining cells (0x0058)
  D/dalvikvm(  149): 0x4d487070 (0070): .word (0x45c968ae)
  D/dalvikvm(  149): End Ljava/io/File;fixSlashes, 3 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for hasNext, offset 0
  D/dalvikvm(  149): 0x45d85478: 0x0070 invoke-direct v1
  D/dalvikvm(  149): TRACEINFO (2): 0x45d85478 Llibcore/util/CollectionUtils$1$1;hasNext.()Z 0 3 of 11, 6 blocks
  D/dalvikvm(  149): Compiling Llibcore/util/CollectionUtils$1$1; hasNext
  D/dalvikvm(  149): 11 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0000 - 0000 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0000)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0000 - 0000)
  D/dalvikvm(  149):   Taken branch: block 3 (0000)
  D/dalvikvm(  149):   Fallthrough : block 2 (0003)
  D/dalvikvm(  149): Block 2 (Hot Chaining Cell) (insn 0003 - 0003 empty)
  D/dalvikvm(  149): Block 3 (Singleton Chaining Cell) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45d85478
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487074
  D/dalvikvm(  149): total size is 148 bytes
  D/dalvikvm(  149): 0x4d487074 (0000): data    0xc02c(49196)
  D/dalvikvm(  149): 0x4d487076 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487078 (0004): data    0x0050(80)
  D/dalvikvm(  149): 0x4d48707a (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48707e (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487080 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487082 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0000
  D/dalvikvm(  149): L0x4ac29ef8:
  D/dalvikvm(  149): -------- dalvik offset: 0x0000 @ invoke-direct v1
  D/dalvikvm(  149): 0x4d487084 (0010): ldr     r0, [r5, #4]
  D/dalvikvm(  149): 0x4d487086 (0012): sub     r7,r5,#24
  D/dalvikvm(  149): 0x4d48708a (0016): cbz     r0,0x4d4870a6 (L0x4ac2a380)
  D/dalvikvm(  149): -------- BARRIER
  D/dalvikvm(  149): 0x4d48708c (0018): stmia   r7, <r0>
  D/dalvikvm(  149): -------- BARRIER
  D/dalvikvm(  149): 0x4d48708e (001a): ldr     r0, [r15pc, #116]
  D/dalvikvm(  149): 0x4d487092 (001e): add     r1, pc, #28
  D/dalvikvm(  149): 0x4d487094 (0020): ldr     r4, [r15pc, #104]
  D/dalvikvm(  149): 0x4d487098 (0024): movs    r7, #2
  D/dalvikvm(  149): 0x4d48709a (0026): movs    r2, #1
  D/dalvikvm(  149): 0x4d48709c (0028): blx_1   0x4d486110
  D/dalvikvm(  149): 0x4d48709e (002a): blx_2   see above
  D/dalvikvm(  149): 0x4d4870a0 (002c): b       0x4d4870bc (L0x4ac29f78)
  D/dalvikvm(  149): 0x4d4870a2 (002e): b       0x4d4870a6 (L0x4ac2a380)
  D/dalvikvm(  149): 0x4d4870a4 (0030): undefined
  D/dalvikvm(  149): L0x4ac2a380:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45d85478 @ +0x0000
  D/dalvikvm(  149): 0x4d4870a6 (0032): ldr     r0, [r15pc, #88]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d4870aa (0036): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d4870ac (0038): blx     r1
  D/dalvikvm(  149): 0x4d4870ae (003a): .align4
  D/dalvikvm(  149): L0x4ac29f38:
  D/dalvikvm(  149): -------- chaining cell (hot): 0x0003
  D/dalvikvm(  149): 0x4d4870b0 (003c): b       0x4d4870b4 (L0x4ac2a940)
  D/dalvikvm(  149): 0x4d4870b2 (003e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a940:
  D/dalvikvm(  149): 0x4d4870b4 (0040): ldr     r0, [r6, #116]
  D/dalvikvm(  149): 0x4d4870b6 (0042): blx     r0
  D/dalvikvm(  149): 0x4d4870b8 (0044): data    0x547e(21630)
  D/dalvikvm(  149): 0x4d4870ba (0046): data    0x45d8(17880)
  D/dalvikvm(  149): 0x4d4870bc (0048): .align4
  D/dalvikvm(  149): L0x4ac29f78:
  D/dalvikvm(  149): -------- chaining cell (invoke singleton): Llibcore/util/CollectionUtils$1$1;computeNext/0x45d8540c
  D/dalvikvm(  149): 0x4d4870bc (0048): b       0x4d4870c0 (L0x4ac2ab40)
  D/dalvikvm(  149): 0x4d4870be (004a): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2ab40:
  D/dalvikvm(  149): 0x4d4870c0 (004c): ldr     r0, [r6, #116]
  D/dalvikvm(  149): 0x4d4870c2 (004e): blx     r0
  D/dalvikvm(  149): 0x4d4870c4 (0050): data    0x540c(21516)
  D/dalvikvm(  149): 0x4d4870c6 (0052): data    0x45d8(17880)
  D/dalvikvm(  149): -------- end of chaining cells (0x0054)
  D/dalvikvm(  149): 0x4d487100 (008c): .word (0x45d85478)
  D/dalvikvm(  149): 0x4d487104 (0090): .word (0x44e73128)
  D/dalvikvm(  149): End Llibcore/util/CollectionUtils$1$1;hasNext, 1 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for next, offset 0x10
  D/dalvikvm(  149): 0x45d06588: 0x0039 if-nez v1, (+8)
  D/dalvikvm(  149): TRACEINFO (3): 0x45d06568 Ljava/util/ArrayList$ArrayListIterator;next.()Ljava/lang/Object; 0x10 2 of 38, 6 blocks
  D/dalvikvm(  149): Compiling Ljava/util/ArrayList$ArrayListIterator; next
  D/dalvikvm(  149): 38 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0010 - 0010 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0010)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0010 - 0010)
  D/dalvikvm(  149):   Taken branch: block 3 (0018)
  D/dalvikvm(  149):   Fallthrough : block 2 (0012)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 0012 - 0012 empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 0018 - 0018 empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45d06588
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487108
  D/dalvikvm(  149): total size is 76 bytes
  D/dalvikvm(  149): 0x4d487108 (0000): data    0xc030(49200)
  D/dalvikvm(  149): 0x4d48710a (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d48710c (0004): data    0x0030(48)
  D/dalvikvm(  149): 0x4d48710e (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d487112 (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487114 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487116 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0010
  D/dalvikvm(  149): L0x4ac29f30:
  D/dalvikvm(  149): -------- dalvik offset: 0x0010 @ if-nez v1, (+8)
  D/dalvikvm(  149): 0x4d487118 (0010): ldr     r0, [r5, #4]
  D/dalvikvm(  149): 0x4d48711a (0012): cmp     r0, #0
  D/dalvikvm(  149): 0x4d48711c (0014): bne     0x4d487130 (L0x4ac29fb0)
  D/dalvikvm(  149): 0x4d487120 (0018): b       0x4d487124 (L0x4ac29f70)
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d487122 (001a): .align4
  D/dalvikvm(  149): L0x4ac29f70:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0012
  D/dalvikvm(  149): 0x4d487124 (001c): b       0x4d487128 (L0x4ac2a4b4)
  D/dalvikvm(  149): 0x4d487126 (001e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a4b4:
  D/dalvikvm(  149): 0x4d487128 (0020): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d48712a (0022): blx     r0
  D/dalvikvm(  149): 0x4d48712c (0024): data    0x658c(25996)
  D/dalvikvm(  149): 0x4d48712e (0026): data    0x45d0(17872)
  D/dalvikvm(  149): 0x4d487130 (0028): .align4
  D/dalvikvm(  149): L0x4ac29fb0:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0018
  D/dalvikvm(  149): 0x4d487130 (0028): b       0x4d487134 (L0x4ac2a6b4)
  D/dalvikvm(  149): 0x4d487132 (002a): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a6b4:
  D/dalvikvm(  149): 0x4d487134 (002c): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487136 (002e): blx     r0
  D/dalvikvm(  149): 0x4d487138 (0030): data    0x6598(26008)
  D/dalvikvm(  149): 0x4d48713a (0032): data    0x45d0(17872)
  D/dalvikvm(  149): -------- end of chaining cells (0x0034)
  D/dalvikvm(  149): End Ljava/util/ArrayList$ArrayListIterator;next, 1 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for computeNext, offset 0x3
  D/dalvikvm(  149): 0x45d85412: 0x00f4 +iget-object-quick v0, v1, (#12)
  D/dalvikvm(  149): 0x45d85416: 0x0039 if-nez v0, (+28)
  D/dalvikvm(  149): TRACEINFO (4): 0x45d8540c Llibcore/util/CollectionUtils$1$1;computeNext.()V 0x3 4 of 46, 6 blocks
  D/dalvikvm(  149): Compiling Llibcore/util/CollectionUtils$1$1; computeNext
  D/dalvikvm(  149): 46 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0003 - 0003 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0003)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0003 - 0005)
  D/dalvikvm(  149):   Taken branch: block 3 (002d)
  D/dalvikvm(  149):   Fallthrough : block 2 (0007)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 0007 - 0007 empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 002d - 002d empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45d85412
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487154
  D/dalvikvm(  149): total size is 96 bytes
  D/dalvikvm(  149): 0x4d487154 (0000): data    0xc034(49204)
  D/dalvikvm(  149): 0x4d487156 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487158 (0004): data    0x0040(64)
  D/dalvikvm(  149): 0x4d48715a (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48715e (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487160 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487162 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0003
  D/dalvikvm(  149): L0x4ac29fa0:
  D/dalvikvm(  149): -------- dalvik offset: 0x0003 @ +iget-object-quick v0, v1, (#12)
  D/dalvikvm(  149): 0x4d487164 (0010): ldr     r0, [r5, #4]
  D/dalvikvm(  149): 0x4d487166 (0012): cbz     r0,0x4d487176 (L0x4ac2a404)
  D/dalvikvm(  149): 0x4d487168 (0014): ldr     r1, [r0, #12]
  D/dalvikvm(  149): -------- dalvik offset: 0x0005 @ if-nez v0, (+28)
  D/dalvikvm(  149): 0x4d48716a (0016): cmp     r1, #0
  D/dalvikvm(  149): 0x4d48716c (0018): str     r1, [r5, #0]
  D/dalvikvm(  149): 0x4d48716e (001a): bne     0x4d48718c (L0x4ac2a020)
  D/dalvikvm(  149): 0x4d487172 (001e): b       0x4d487180 (L0x4ac29fe0)
  D/dalvikvm(  149): 0x4d487174 (0020): undefined
  D/dalvikvm(  149): L0x4ac2a404:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45d85412 @ +0x0003
  D/dalvikvm(  149): 0x4d487176 (0022): ldr     r0, [r15pc, #56]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d48717a (0026): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d48717c (0028): blx     r1
  D/dalvikvm(  149): 0x4d48717e (002a): .align4
  D/dalvikvm(  149): L0x4ac29fe0:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0007
  D/dalvikvm(  149): 0x4d487180 (002c): b       0x4d487184 (L0x4ac2a8e4)
  D/dalvikvm(  149): 0x4d487182 (002e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a8e4:
  D/dalvikvm(  149): 0x4d487184 (0030): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487186 (0032): blx     r0
  D/dalvikvm(  149): 0x4d487188 (0034): data    0x541a(21530)
  D/dalvikvm(  149): 0x4d48718a (0036): data    0x45d8(17880)
  D/dalvikvm(  149): 0x4d48718c (0038): .align4
  D/dalvikvm(  149): L0x4ac2a020:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x002d
  D/dalvikvm(  149): 0x4d48718c (0038): b       0x4d487190 (L0x4ac2aae4)
  D/dalvikvm(  149): 0x4d48718e (003a): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2aae4:
  D/dalvikvm(  149): 0x4d487190 (003c): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487192 (003e): blx     r0
  D/dalvikvm(  149): 0x4d487194 (0040): data    0x5466(21606)
  D/dalvikvm(  149): 0x4d487196 (0042): data    0x45d8(17880)
  D/dalvikvm(  149): -------- end of chaining cells (0x0044)
  D/dalvikvm(  149): 0x4d4871b0 (005c): .word (0x45d85412)
  D/dalvikvm(  149): End Llibcore/util/CollectionUtils$1$1;computeNext, 2 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for computeNext, offset 0
  D/dalvikvm(  149): 0x45d8540c: 0x0012 const/4 v0, (#0), (#0)
  D/dalvikvm(  149): 0x45d8540e: 0x00f5 +iput-quick v0, v1, (#20)
  D/PowerManagerService(  149): system ready!
  D/dalvikvm(  149): 0x45d85412: 0x00f4 +iget-object-quick v0, v1, (#12)
  D/dalvikvm(  149): 0x45d85416: 0x0039 if-nez v0, (+28)
  D/dalvikvm(  149): TRACEINFO (5): 0x45d8540c Llibcore/util/CollectionUtils$1$1;computeNext.()V 0 7 of 46, 6 blocks
  D/dalvikvm(  149): Compiling Llibcore/util/CollectionUtils$1$1; computeNext
  D/dalvikvm(  149): 46 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0000 - 0000 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0000)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0000 - 0005)
  D/dalvikvm(  149):   Taken branch: block 3 (002d)
  D/dalvikvm(  149):   Fallthrough : block 2 (0007)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 0007 - 0007 empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 002d - 002d empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45d8540c
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d4871b4
  D/dalvikvm(  149): total size is 100 bytes
  D/dalvikvm(  149): 0x4d4871b4 (0000): data    0xc038(49208)
  D/dalvikvm(  149): 0x4d4871b6 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d4871b8 (0004): data    0x0044(68)
  D/dalvikvm(  149): 0x4d4871ba (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d4871be (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d4871c0 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d4871c2 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0000
  I/ActivityManager(  149): System now ready
  D/dalvikvm(  149): L0x4ac2a0c0:
  I/SystemServer(  149): Making services ready
  D/dalvikvm(  149): -------- dalvik offset: 0x0000 @ const/4 v0, (#0), (#0)
  D/dalvikvm(  149): 0x4d4871c4 (0010): ldr     r1, [r5, #4]
  D/dalvikvm(  149): 0x4d4871c6 (0012): movs    r0, #0
  D/dalvikvm(  149): -------- dalvik offset: 0x0001 @ +iput-quick v0, v1, (#20)
  D/dalvikvm(  149): 0x4d4871c8 (0014): str     r0, [r5, #0]
  D/dalvikvm(  149): 0x4d4871ca (0016): cbz     r1,0x4d4871dc (L0x4ac2a680)
  D/dalvikvm(  149): 0x4d4871cc (0018): str     r0, [r1, #20]
  D/dalvikvm(  149): -------- dalvik offset: 0x0003 @ +iget-object-quick v0, v1, (#12)
  D/dalvikvm(  149): 0x4d4871ce (001a): ldr     r0, [r1, #12]
  D/dalvikvm(  149): -------- dalvik offset: 0x0005 @ if-nez v0, (+28)
  D/dalvikvm(  149): 0x4d4871d0 (001c): cmp     r0, #0
  D/dalvikvm(  149): 0x4d4871d2 (001e): str     r0, [r5, #0]
  D/dalvikvm(  149): 0x4d4871d4 (0020): bne     0x4d4871f0 (L0x4ac2a140)
  D/dalvikvm(  149): 0x4d4871d8 (0024): b       0x4d4871e4 (L0x4ac2a100)
  D/dalvikvm(  149): 0x4d4871da (0026): undefined
  D/dalvikvm(  149): L0x4ac2a680:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45d8540e @ +0x0001
  D/dalvikvm(  149): 0x4d4871dc (0028): ldr     r0, [r15pc, #52]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d4871e0 (002c): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d4871e2 (002e): blx     r1
  D/dalvikvm(  149): 0x4d4871e4 (0030): .align4
  D/SystemServer(  149): Starting service: Intent { cmp=com.android.systemui/.SystemUIService }
  I/Zygote  (  149): Process: zygote socket opened
  D/dalvikvm(  149): L0x4ac2a100:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0007
  D/dalvikvm(  149): 0x4d4871e4 (0030): b       0x4d4871e8 (L0x4ac2acdc)
  D/dalvikvm(  149): 0x4d4871e6 (0032): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2acdc:
  D/dalvikvm(  149): 0x4d4871e8 (0034): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d4871ea (0036): blx     r0
  D/dalvikvm(  149): 0x4d4871ec (0038): data    0x541a(21530)
  D/dalvikvm(  149): 0x4d4871ee (003a): data    0x45d8(17880)
  D/dalvikvm(  149): 0x4d4871f0 (003c): .align4
  D/dalvikvm(  149): L0x4ac2a140:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x002d
  D/dalvikvm(  149): 0x4d4871f0 (003c): b       0x4d4871f4 (L0x4ac2aedc)
  D/dalvikvm(  149): 0x4d4871f2 (003e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2aedc:
  D/dalvikvm(  149): 0x4d4871f4 (0040): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d4871f6 (0042): blx     r0
  D/dalvikvm(  149): 0x4d4871f8 (0044): data    0x5466(21606)
  D/dalvikvm(  149): 0x4d4871fa (0046): data    0x45d8(17880)
  D/dalvikvm(  149): -------- end of chaining cells (0x0048)
  D/dalvikvm(  149): 0x4d487214 (0060): .word (0x45d8540e)
  D/dalvikvm(  149): End Llibcore/util/CollectionUtils$1$1;computeNext, 4 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for fixSlashes, offset 0x9
  D/dalvikvm(  149): 0x45c968aa: 0x0035 if-ge v1, v3, (+1b)
  D/dalvikvm(  149): TRACEINFO (6): 0x45c96898 Ljava/io/File;fixSlashes.(Ljava/lang/String;)Ljava/lang/String; 0x9 2 of 56, 6 blocks
  D/dalvikvm(  149): Compiling Ljava/io/File; fixSlashes
  D/dalvikvm(  149): 56 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0009 - 0009 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0009)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0009 - 0009)
  D/dalvikvm(  149):   Taken branch: block 3 (0024)
  D/dalvikvm(  149):   Fallthrough : block 2 (000b)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 000b - 000b empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 0024 - 0024 empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45c968aa
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487218
  D/dalvikvm(  149): total size is 76 bytes
  D/dalvikvm(  149): 0x4d487218 (0000): data    0xc03c(49212)
  D/dalvikvm(  149): 0x4d48721a (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d48721c (0004): data    0x0030(48)
  D/dalvikvm(  149): 0x4d48721e (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d487222 (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487224 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487226 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0009
  D/dalvikvm(  149): L0x4ac29f98:
  D/dalvikvm(  149): -------- dalvik offset: 0x0009 @ if-ge v1, v3, (+1b)
  D/dalvikvm(  149): 0x4d487228 (0010): ldr     r0, [r5, #4]
  D/dalvikvm(  149): 0x4d48722a (0012): ldr     r1, [r5, #12]
  D/dalvikvm(  149): 0x4d48722c (0014): cmp     r0, r1
  D/dalvikvm(  149): 0x4d48722e (0016): bge     0x4d487240 (L0x4ac2a018)
  D/dalvikvm(  149): 0x4d487232 (001a): b       0x4d487234 (L0x4ac29fd8)
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d487234 (001c): .align4
  D/dalvikvm(  149): L0x4ac29fd8:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x000b
  D/dalvikvm(  149): 0x4d487234 (001c): b       0x4d487238 (L0x4ac2a568)
  D/dalvikvm(  149): 0x4d487236 (001e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a568:
  D/dalvikvm(  149): 0x4d487238 (0020): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d48723a (0022): blx     r0
  D/dalvikvm(  149): 0x4d48723c (0024): data    0x68ae(26798)
  D/dalvikvm(  149): 0x4d48723e (0026): data    0x45c9(17865)
  I/ActivityManager(  149): Start proc com.android.systemui for service com.android.systemui/.SystemUIService: pid=213 uid=10023 gids={1028, 1015, 3002, 3001}
  D/NetworkManagementService(  149): not enabling bandwidth control
  W/NetworkStats(  149): bandwidth controls disabled, unable to track stats
  W/NetworkPolicy(  149): bandwidth controls disabled, unable to enforce policy
  I/ActivityManager(  149): Config changed: {1.0 0mcc0mnc en_US sw320dp w320dp h455dp nrml port -touch -keyb/v/h tball/v s.3}
  W/RecognitionManagerService(  149): no available voice recognition services found
  D/dalvikvm(  149): 0x4d487240 (0028): .align4
  D/dalvikvm(  149): L0x4ac2a018:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0024
  D/dalvikvm(  149): 0x4d487240 (0028): b       0x4d487244 (L0x4ac2a768)
  D/dalvikvm(  149): 0x4d487242 (002a): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a768:
  D/dalvikvm(  149): 0x4d487244 (002c): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487246 (002e): blx     r0
  D/dalvikvm(  149): 0x4d487248 (0030): data    0x68e0(26848)
  D/dalvikvm(  149): 0x4d48724a (0032): data    0x45c9(17865)
  D/dalvikvm(  149): -------- end of chaining cells (0x0034)
  D/dalvikvm(  149): End Ljava/io/File;fixSlashes, 1 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for fixSlashes, offset 0x1e
  D/dalvikvm(  149): 0x45c968d4: 0x00d8 add-int/lit8 v4, v5, (#1)
  D/dalvikvm(  149): 0x45c968d8: 0x0050 aput-char v0, v6, v5
  D/dalvikvm(  149): 0x45c968dc: 0x0012 const/4 v2, (#0), (#0)
  D/dalvikvm(  149): 0x45c968de: 0x0028 goto (-9)
  D/dalvikvm(  149): 0x45c968cc: 0x00d8 add-int/lit8 v1, v1, (#1)
  D/dalvikvm(  149): 0x45c968d0: 0x0001 move v5, v4, (#0)
  D/dalvikvm(  149): 0x45c968d2: 0x0028 goto (-14)
  D/dalvikvm(  149): 0x45c968aa: 0x0035 if-ge v1, v3, (+1b)
  V/LockPatternKeyguardView(  149): Set visibility on com.android.internal.policy.impl.LockPatternKeyguardView$4@411d7980 to 0
  D/dalvikvm(  149): Loop trace @ offset 001e
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487264
  D/dalvikvm(  149): total size is 256 bytes
  D/dalvikvm(  149): 0x4d487264 (0000): data    0xc040(49216)
  D/dalvikvm(  149): 0x4d487266 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487268 (0004): data    0x00c4(196)
  D/dalvikvm(  149): 0x4d48726a (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48726e (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487270 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487272 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x001e
  D/dalvikvm(  149): L0x49df170c:
  D/dalvikvm(  149): -------- kMirOpPhi
  D/dalvikvm(  149): -------- kMirOpPhi
  D/dalvikvm(  149): -------- kMirOpPhi
  D/dalvikvm(  149): -------- dalvik offset: 0x001e @ add-int/lit8 v4, v5, (#1)
  D/dalvikvm(  149): 0x4d487274 (0010): ldr     r0, [r5, #20]
  D/dalvikvm(  149): 0x4d487276 (0012): ldr     r2, [r5, #24]
  D/dalvikvm(  149): 0x4d487278 (0014): adds    r1, r0, #1
  D/dalvikvm(  149): -------- dalvik offset: 0x0020 @ aput-char v0, v6, v5
  D/dalvikvm(  149): 0x4d48727a (0016): str     r1, [r5, #16]
  D/dalvikvm(  149): 0x4d48727c (0018): cbz     r2,0x4d4872ee (L0x49df222c)
  D/dalvikvm(  149): 0x4d48727e (001a): ldr     r3, [r2, #8]
  D/dalvikvm(  149): 0x4d487280 (001c): adds    r2, r2, #16
  D/dalvikvm(  149): 0x4d487282 (001e): ldr     r4, [r5, #0]
  D/dalvikvm(  149): 0x4d487284 (0020): cmp     r0, r3
  D/dalvikvm(  149): 0x4d487286 (0022): bcs     0x4d4872ee (L0x49df222c)
  D/dalvikvm(  149): 0x4d48728a (0026): ldrb    r8, [r6, #42]
  D/dalvikvm(  149): 0x4d48728e (002a): strh    r4, [r2, r0, LSL #1]
  D/dalvikvm(  149): -------- dalvik offset: 0x0022 @ const/4 v2, (#0), (#0)
  D/dalvikvm(  149): 0x4d487292 (002e): movs    r7, #0
  D/dalvikvm(  149): -------- dalvik offset: 0x0023 @ goto (-9)
  D/dalvikvm(  149): 0x4d487294 (0030): cmp     r8, #0 [0]
  D/dalvikvm(  149): 0x4d487298 (0034): ldr     r9, [r5, #4]
  D/dalvikvm(  149): 0x4d48729c (0038): str     r7, [r5, #8]
  D/dalvikvm(  149): 0x4d48729e (003a): bne     0x4d4872f4 (L0x49df26a4)
  D/dalvikvm(  149): -------- dalvik offset: 0x001a @ add-int/lit8 v1, v1, (#1)
  D/dalvikvm(  149): 0x4d4872a0 (003c): ldrb    r10, [r6, #42]
  D/dalvikvm(  149): 0x4d4872a4 (0040): add     r9,r9,#1
  D/dalvikvm(  149): -------- dalvik offset: 0x001c @ move v5, v4, (#0)
  D/dalvikvm(  149): 0x4d4872a8 (0044): movs    r0, r1
  D/dalvikvm(  149): -------- dalvik offset: 0x001d @ goto (-14)
  D/dalvikvm(  149): 0x4d4872aa (0046): cmp     r10, #0 [0]
  D/dalvikvm(  149): 0x4d4872ae (004a): str     r0, [r5, #20]
  D/dalvikvm(  149): 0x4d4872b0 (004c): ldr     r11, [r5, #12]
  D/dalvikvm(  149): 0x4d4872b4 (0050): str     r9, [r5, #4]
  D/dalvikvm(  149): 0x4d4872b8 (0054): bne     0x4d4872fa (L0x49df2b14)
  D/dalvikvm(  149): -------- dalvik offset: 0x0009 @ if-ge v1, v3, (+1b)
  D/dalvikvm(  149): 0x4d4872ba (0056): cmp     r9, r11
  D/dalvikvm(  149): 0x4d4872bc (0058): bge     0x4d487308 (L0x49df17cc)
  D/dalvikvm(  149): L0x49df180c:
  D/dalvikvm(  149): -------- dalvik offset: 0x000b @ aget-char v0, v6, v1
  D/dalvikvm(  149): 0x4d4872c0 (005c): ldr     r12, [r5, #24]
  D/dalvikvm(  149): 0x4d4872c4 (0060): ldr     r0, [r5, #4]
  D/dalvikvm(  149): 0x4d4872c6 (0062): cmp     r12, #0 [0]
  D/dalvikvm(  149): 0x4d4872ca (0066): beq     0x4d487300 (L0x49df3138)
  D/dalvikvm(  149): 0x4d4872cc (0068): ldr     r2, [r12, #8]
  D/dalvikvm(  149): 0x4d4872d0 (006c): add     r1,r12,#16
  D/dalvikvm(  149): 0x4d4872d4 (0070): cmp     r0, r2
  D/dalvikvm(  149): 0x4d4872d6 (0072): bcs     0x4d487300 (L0x49df3138)
  D/dalvikvm(  149): 0x4d4872da (0076): ldrh    r3, [r1, r0, LSL #1]
  D/dalvikvm(  149): -------- dalvik offset: 0x000d @ const/16 v7, (#47), (#0)
  D/dalvikvm(  149): 0x4d4872de (007a): movs    r4, #47
  D/dalvikvm(  149): -------- dalvik offset: 0x000f @ if-ne v0, v7, (+f)
  D/dalvikvm(  149): 0x4d4872e0 (007c): cmp     r3, r4
  D/dalvikvm(  149): 0x4d4872e2 (007e): str     r4, [r5, #28]
  D/dalvikvm(  149): 0x4d4872e4 (0080): str     r3, [r5, #0]
  D/dalvikvm(  149): 0x4d4872e6 (0082): bne     0x4d487274 (L0x49df170c)
  D/dalvikvm(  149): 0x4d4872ea (0086): b       0x4d487314 (L0x49df19cc)
  D/dalvikvm(  149): 0x4d4872ec (0088): undefined
  D/dalvikvm(  149): L0x49df222c:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45c968d8 @ +0x0020
  D/dalvikvm(  149): 0x4d4872ee (008a): ldr     r0, [r15pc, #112]
  D/dalvikvm(  149): 0x4d4872f2 (008e): b       0x4d487304 (L0x49df1b0c)
  D/dalvikvm(  149): L0x49df26a4:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45c968de @ +0x0023
  D/dalvikvm(  149): 0x4d4872f4 (0090): ldr     r0, [r15pc, #100]
  D/dalvikvm(  149): 0x4d4872f8 (0094): b       0x4d487304 (L0x49df1b0c)
  D/dalvikvm(  149): L0x49df2b14:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45c968d2 @ +0x001d
  D/dalvikvm(  149): 0x4d4872fa (0096): ldr     r0, [r15pc, #92]
  D/dalvikvm(  149): 0x4d4872fe (009a): b       0x4d487304 (L0x49df1b0c)
  D/dalvikvm(  149): L0x49df3138:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45c968ae @ +0x000b
  D/dalvikvm(  149): 0x4d487300 (009c): ldr     r0, [r15pc, #80]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d487304 (00a0): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d487306 (00a2): blx     r1
  D/dalvikvm(  149): 0x4d487308 (00a4): .align4
  D/dalvikvm(  149): L0x49df17cc:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0024
  D/dalvikvm(  149): 0x4d487308 (00a4): b       0x4d48730c (L0x49df3b34)
  D/dalvikvm(  149): 0x4d48730a (00a6): orrs    r0, r0
  D/dalvikvm(  149): L0x49df3b34:
  D/dalvikvm(  149): 0x4d48730c (00a8): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d48730e (00aa): blx     r0
  D/dalvikvm(  149): 0x4d487310 (00ac): data    0x68e0(26848)
  D/dalvikvm(  149): 0x4d487312 (00ae): data    0x45c9(17865)
  D/dalvikvm(  149): 0x4d487314 (00b0): .align4
  D/dalvikvm(  149): L0x49df19cc:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0011
  D/dalvikvm(  149): 0x4d487314 (00b0): b       0x4d487318 (L0x49df3d34)
  D/dalvikvm(  149): 0x4d487316 (00b2): orrs    r0, r0
  D/dalvikvm(  149): L0x49df3d34:
  D/dalvikvm(  149): 0x4d487318 (00b4): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d48731a (00b6): blx     r0
  D/dalvikvm(  149): 0x4d48731c (00b8): data    0x68ba(26810)
  D/dalvikvm(  149): 0x4d48731e (00ba): data    0x45c9(17865)
  D/dalvikvm(  149): 0x4d487320 (00bc): .align4
  D/dalvikvm(  149): L0x49df1a8c:
  D/dalvikvm(  149): -------- chaining cell (backward branch): 0x0000
  D/dalvikvm(  149): 0x4d487320 (00bc): b       0x4d487324 (L0x49df3f34)
  D/dalvikvm(  149): 0x4d487322 (00be): orrs    r0, r0
  D/dalvikvm(  149): L0x49df3f34:
  D/dalvikvm(  149): 0x4d487324 (00c0): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487326 (00c2): blx     r0
  D/dalvikvm(  149): 0x4d487328 (00c4): data    0x6898(26776)
  D/dalvikvm(  149): 0x4d48732a (00c6): data    0x45c9(17865)
  D/dalvikvm(  149): -------- end of chaining cells (0x00c8)
  D/dalvikvm(  149): 0x4d487354 (00f0): .word (0x45c968ae)
  D/dalvikvm(  149): 0x4d487358 (00f4): .word (0x45c968d2)
  D/dalvikvm(  149): 0x4d48735c (00f8): .word (0x45c968de)
  D/dalvikvm(  149): 0x4d487360 (00fc): .word (0x45c968d8)
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for toUpperCase, offset 0xc0
  D/dalvikvm(  149): 0x45ca5aec: 0x0001 move v4, v5, (#0)
  D/dalvikvm(  149): 0x45ca5aee: 0x0028 goto (-40)
  D/dalvikvm(  149): 0x45ca5a6e: 0x00d8 add-int/lit8 v9, v9, (#1)
  D/dalvikvm(  149): 0x45ca5a72: 0x0001 move v5, v4, (#0)
  D/dalvikvm(  149): 0x45ca5a74: 0x0028 goto (-56)
  D/dalvikvm(  149): 0x45ca59c8: 0x0035 if-ge v9, v3, (+ba)
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for toUpperCase, offset 0xc0
  D/dalvikvm(  149): 0x45ca5aec: 0x0001 move v4, v5, (#0)
  D/dalvikvm(  149): 0x45ca5aee: 0x0028 goto (-40)
  D/dalvikvm(  149): 0x45ca5a6e: 0x00d8 add-int/lit8 v9, v9, (#1)
  D/dalvikvm(  149): 0x45ca5a72: 0x0001 move v5, v4, (#0)
  D/dalvikvm(  149): 0x45ca5a74: 0x0028 goto (-56)
  D/dalvikvm(  149): 0x45ca59c8: 0x0035 if-ge v9, v3, (+ba)
  D/dalvikvm(  149): TRACEINFO (9): 0x45ca596c Ljava/lang/CaseMapper;toUpperCase.(Ljava/util/Locale;Ljava/lang/String;[CII)Ljava/lang/String; 0xc0 8 of 273, 8 blocks
  D/dalvikvm(  149): Compiling Ljava/lang/CaseMapper; toUpperCase
  D/dalvikvm(  149): 273 insns
  D/dalvikvm(  149): 8 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 00c0 - 00c0 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (00c0)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 00c0 - 00c1)
  D/dalvikvm(  149):   Taken branch: block 2 (0081)
  D/dalvikvm(  149): Block 2 (Code Block) (insn 0081 - 0084)
  D/dalvikvm(  149):   Taken branch: block 3 (002e)
  D/dalvikvm(  149): Block 3 (Code Block) (insn 002e - 002e)
  D/dalvikvm(  149):   Taken branch: block 5 (00e8)
  D/dalvikvm(  149):   Fallthrough : block 4 (0030)
  D/dalvikvm(  149): Block 4 (Normal Chaining Cell) (insn 0030 - 0030 empty)
  D/dalvikvm(  149): Block 5 (Normal Chaining Cell) (insn 00e8 - 00e8 empty)
  D/dalvikvm(  149): Block 6 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 7 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45ca5aec
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487364
  D/dalvikvm(  149): total size is 104 bytes
  D/dalvikvm(  149): 0x4d487364 (0000): data    0xc044(49220)
  D/dalvikvm(  149): 0x4d487366 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487368 (0004): data    0x003c(60)
  D/dalvikvm(  149): 0x4d48736a (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48736e (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487370 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487372 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x00c0
  D/dalvikvm(  149): L0x4ac2a5ec:
  D/dalvikvm(  149): -------- dalvik offset: 0x00c0 @ move v4, v5, (#0)
  D/dalvikvm(  149): 0x4d487374 (0010): ldr     r0, [r5, #20]
  D/dalvikvm(  149): -------- dalvik offset: 0x00c1 @ goto (-40)
  D/dalvikvm(  149): -------- dalvik offset: 0x0081 @ add-int/lit8 v9, v9, (#1)
  D/dalvikvm(  149): 0x4d487376 (0012): ldr     r1, [r5, #36]
  D/dalvikvm(  149): 0x4d487378 (0014): ldr     r3, [r5, #12]
  D/dalvikvm(  149): 0x4d48737a (0016): adds    r1, r1, #1
  D/dalvikvm(  149): -------- dalvik offset: 0x0083 @ move v5, v4, (#0)
  D/dalvikvm(  149): 0x4d48737c (0018): movs    r2, r0
  D/dalvikvm(  149): -------- dalvik offset: 0x0084 @ goto (-56)
  D/dalvikvm(  149): -------- dalvik offset: 0x002e @ if-ge v9, v3, (+ba)
  D/dalvikvm(  149): 0x4d48737e (001a): cmp     r1, r3
  D/dalvikvm(  149): 0x4d487380 (001c): str     r2, [r5, #20]
  D/dalvikvm(  149): 0x4d487382 (001e): str     r1, [r5, #36]
  D/dalvikvm(  149): 0x4d487384 (0020): str     r0, [r5, #16]
  D/dalvikvm(  149): 0x4d487386 (0022): bge     0x4d487398 (L0x4ac2a6ec)
  D/dalvikvm(  149): 0x4d48738a (0026): b       0x4d48738c (L0x4ac2a6ac)
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d48738c (0028): .align4
  D/dalvikvm(  149): L0x4ac2a6ac:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0030
  D/dalvikvm(  149): 0x4d48738c (0028): b       0x4d487390 (L0x4ac2b228)
  D/dalvikvm(  149): 0x4d48738e (002a): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2b228:
  D/dalvikvm(  149): 0x4d487390 (002c): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487392 (002e): blx     r0
  D/dalvikvm(  149): 0x4d487394 (0030): data    0x59cc(22988)
  D/dalvikvm(  149): 0x4d487396 (0032): data    0x45ca(17866)
  D/dalvikvm(  149): 0x4d487398 (0034): .align4
  D/dalvikvm(  149): L0x4ac2a6ec:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x00e8
  D/dalvikvm(  149): 0x4d487398 (0034): b       0x4d48739c (L0x4ac2b428)
  D/dalvikvm(  149): 0x4d48739a (0036): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2b428:
  D/dalvikvm(  149): 0x4d48739c (0038): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d48739e (003a): blx     r0
  D/dalvikvm(  149): 0x4d4873a0 (003c): data    0x5b3c(23356)
  D/dalvikvm(  149): 0x4d4873a2 (003e): data    0x45ca(17866)
  D/dalvikvm(  149): -------- end of chaining cells (0x0040)
  D/dalvikvm(  149): End Ljava/lang/CaseMapper;toUpperCase, 6 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for hashCode, offset 0x16
  D/dalvikvm(  149): 0x45cb4180: 0x00da mul-int/lit8 v4, v2, (#31)
  D/dalvikvm(  149): 0x45cb4184: 0x0049 aget-char v5, v0, v3
  D/dalvikvm(  149): 0x45cb4188: 0x0090 add-int v2, v4, v5
  D/dalvikvm(  149): 0x45cb418c: 0x00d8 add-int/lit8 v3, v3, (#1)
  D/dalvikvm(  149): 0x45cb4190: 0x0028 goto (-a)
  D/dalvikvm(  149): 0x45cb417c: 0x0035 if-ge v3, v1, (+b)
  D/dalvikvm(  149): Loop trace @ offset 0016
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d4873cc
  D/dalvikvm(  149): total size is 184 bytes
  D/dalvikvm(  149): 0x4d4873cc (0000): data    0xc048(49224)
  D/dalvikvm(  149): 0x4d4873ce (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d4873d0 (0004): data    0x008c(140)
  D/dalvikvm(  149): 0x4d4873d2 (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d4873d6 (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d4873d8 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d4873da (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0016
  D/dalvikvm(  149): -------- kMirOpNullNRangeUpCheck
  D/dalvikvm(  149): 0x4d4873dc (0010): ldr     r0, [r5, #0]
  D/dalvikvm(  149): 0x4d4873de (0012): ldr     r1, [r5, #4]
  D/dalvikvm(  149): 0x4d4873e0 (0014): cbz     r0,0x4d4873f4 (L0x4ac2aed4)
  D/dalvikvm(  149): 0x4d4873e2 (0016): ldr     r2, [r0, #8]
  D/dalvikvm(  149): 0x4d4873e4 (0018): subs    r3, r1, #1]
  D/dalvikvm(  149): 0x4d4873e6 (001a): cmp     r3, r2
  D/dalvikvm(  149): 0x4d4873e8 (001c): bge     0x4d4873f4 (L0x4ac2aed4)
  D/dalvikvm(  149): -------- kMirOpLowerBound
  D/dalvikvm(  149): 0x4d4873ec (0020): ldr     r4, [r5, #12]
  D/dalvikvm(  149): 0x4d4873ee (0022): cmp     r4, #0
  D/dalvikvm(  149): 0x4d4873f0 (0024): blt     0x4d4873f4 (L0x4ac2aed4)
  D/dalvikvm(  149): 0x4d4873f2 (0026): b       0x4d4873f6 (L0x4ac2aaac)
  D/dalvikvm(  149): 0x4d4873f4 (0028): b       0x4d487436 (L0x4ac2ae54)
  D/dalvikvm(  149): L0x4ac2aaac:
  D/dalvikvm(  149): -------- kMirOpPhi
  D/dalvikvm(  149): -------- kMirOpPhi
  D/dalvikvm(  149): -------- dalvik offset: 0x0016 @ mul-int/lit8 v4, v2, (#31)
  D/dalvikvm(  149): 0x4d4873f6 (002a): ldr     r7, [r5, #8]
  D/dalvikvm(  149): 0x4d4873f8 (002c): ldr     r10, [r5, #0]
  D/dalvikvm(  149): 0x4d4873fc (0030): ldr     r11, [r5, #12]
  D/dalvikvm(  149): 0x4d487400 (0034): lsl     r9, r7, #5
  D/dalvikvm(  149): 0x4d487404 (0038): subs    r8, r9, r7
  D/dalvikvm(  149): -------- dalvik offset: 0x0018 @ aget-char v5, v0, v3
  D/dalvikvm(  149): 0x4d487408 (003c): add     r12,r10,#16
  D/dalvikvm(  149): 0x4d48740c (0040): ldrh    r0, [r12, r11, LSL #1]
  D/dalvikvm(  149): -------- dalvik offset: 0x001a @ add-int v2, v4, v5
  D/dalvikvm(  149): 0x4d487410 (0044): ldrb    r1, [r6, #42]
  D/dalvikvm(  149): 0x4d487414 (0048): adds    r7, r8, r0
  D/dalvikvm(  149): -------- dalvik offset: 0x001c @ add-int/lit8 v3, v3, (#1)
  D/dalvikvm(  149): 0x4d487418 (004c): add     r11,r11,#1
  D/dalvikvm(  149): -------- dalvik offset: 0x001e @ goto (-a)
  D/dalvikvm(  149): 0x4d48741c (0050): str     r11, [r5, #12]
  D/dalvikvm(  149): 0x4d487420 (0054): str     r7, [r5, #8]
  D/dalvikvm(  149): 0x4d487422 (0056): str     r0, [r5, #20]
  D/dalvikvm(  149): 0x4d487424 (0058): ldr     r2, [r5, #4]
  D/dalvikvm(  149): 0x4d487426 (005a): str     r8, [r5, #16]
  D/dalvikvm(  149): 0x4d48742a (005e): cbnz    r1,0x4d48743c (L0x49df19f8)
  D/dalvikvm(  149): -------- dalvik offset: 0x0014 @ if-ge v3, v1, (+b)
  D/dalvikvm(  149): 0x4d48742c (0060): cmp     r11, r2
  D/dalvikvm(  149): 0x4d48742e (0062): bge     0x4d487444 (L0x4ac2ab2c)
  D/dalvikvm(  149): 0x4d487432 (0066): b       0x4d4873f6 (L0x4ac2aaac)
  D/dalvikvm(  149): 0x4d487434 (0068): undefined
  D/dalvikvm(  149): L0x4ac2ae54:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45cb4180 @ +0x0016
  D/dalvikvm(  149): 0x4d487436 (006a): ldr     r0, [r15pc, #72]
  D/dalvikvm(  149): 0x4d48743a (006e): b       0x4d487440 (L0x4ac2ac2c)
  D/dalvikvm(  149): L0x49df19f8:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45cb4190 @ +0x001e
  D/dalvikvm(  149): 0x4d48743c (0070): ldr     r0, [r15pc, #60]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d487440 (0074): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d487442 (0076): blx     r1
  D/dalvikvm(  149): 0x4d487444 (0078): .align4
  D/dalvikvm(  149): L0x4ac2ab2c:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x001f
  D/dalvikvm(  149): 0x4d487444 (0078): b       0x4d487448 (L0x49df20e0)
  D/dalvikvm(  149): 0x4d487446 (007a): orrs    r0, r0
  D/dalvikvm(  149): L0x49df20e0:
  D/dalvikvm(  149): 0x4d487448 (007c): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d48744a (007e): blx     r0
  D/dalvikvm(  149): 0x4d48744c (0080): data    0x4192(16786)
  D/dalvikvm(  149): 0x4d48744e (0082): data    0x45cb(17867)
  D/dalvikvm(  149): 0x4d487450 (0084): .align4
  D/dalvikvm(  149): L0x4ac2abac:
  D/dalvikvm(  149): -------- chaining cell (backward branch): 0x0000
  D/dalvikvm(  149): 0x4d487450 (0084): b       0x4d487454 (L0x49df22e0)
  D/dalvikvm(  149): 0x4d487452 (0086): orrs    r0, r0
  D/dalvikvm(  149): L0x49df22e0:
  D/dalvikvm(  149): 0x4d487454 (0088): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487456 (008a): blx     r0
  D/dalvikvm(  149): 0x4d487458 (008c): data    0x4154(16724)
  D/dalvikvm(  149): 0x4d48745a (008e): data    0x45cb(17867)
  D/dalvikvm(  149): -------- end of chaining cells (0x0090)
  D/dalvikvm(  149): 0x4d48747c (00b0): .word (0x45cb4190)
  D/dalvikvm(  149): 0x4d487480 (00b4): .word (0x45cb4180)
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for hashCode, offset 0x14
  D/dalvikvm(  149): 0x45cb417c: 0x0035 if-ge v3, v1, (+b)
  D/dalvikvm(  149): TRACEINFO (11): 0x45cb4154 Ljava/lang/String;hashCode.()I 0x14 2 of 35, 6 blocks
  D/dalvikvm(  149): Compiling Ljava/lang/String; hashCode
  D/dalvikvm(  149): 35 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0014 - 0014 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0014)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0014 - 0014)
  D/dalvikvm(  149):   Taken branch: block 3 (001f)
  D/dalvikvm(  149):   Fallthrough : block 2 (0016)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 0016 - 0016 empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 001f - 001f empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45cb417c
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487484
  D/dalvikvm(  149): total size is 76 bytes
  D/dalvikvm(  149): 0x4d487484 (0000): data    0xc04c(49228)
  D/dalvikvm(  149): 0x4d487486 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487488 (0004): data    0x0030(48)
  D/dalvikvm(  149): 0x4d48748a (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48748e (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487490 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487492 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0014
  D/dalvikvm(  149): L0x4ac29f68:
  D/dalvikvm(  149): -------- dalvik offset: 0x0014 @ if-ge v3, v1, (+b)
  D/dalvikvm(  149): 0x4d487494 (0010): ldr     r0, [r5, #12]
  D/dalvikvm(  149): 0x4d487496 (0012): ldr     r1, [r5, #4]
  D/dalvikvm(  149): 0x4d487498 (0014): cmp     r0, r1
  D/dalvikvm(  149): 0x4d48749a (0016): bge     0x4d4874ac (L0x4ac29fe8)
  D/dalvikvm(  149): 0x4d48749e (001a): b       0x4d4874a0 (L0x4ac29fa8)
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d4874a0 (001c): .align4
  D/dalvikvm(  149): L0x4ac29fa8:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0016
  D/dalvikvm(  149): 0x4d4874a0 (001c): b       0x4d4874a4 (L0x4ac2a538)
  D/dalvikvm(  149): 0x4d4874a2 (001e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a538:
  D/dalvikvm(  149): 0x4d4874a4 (0020): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d4874a6 (0022): blx     r0
  D/dalvikvm(  149): 0x4d4874a8 (0024): data    0x4180(16768)
  D/dalvikvm(  149): 0x4d4874aa (0026): data    0x45cb(17867)
  D/dalvikvm(  149): 0x4d4874ac (0028): .align4
  D/dalvikvm(  149): L0x4ac29fe8:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x001f
  D/dalvikvm(  149): 0x4d4874ac (0028): b       0x4d4874b0 (L0x4ac2a738)
  D/dalvikvm(  149): 0x4d4874ae (002a): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a738:
  D/dalvikvm(  149): 0x4d4874b0 (002c): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d4874b2 (002e): blx     r0
  D/dalvikvm(  149): 0x4d4874b4 (0030): data    0x4192(16786)
  D/dalvikvm(  149): 0x4d4874b6 (0032): data    0x45cb(17867)
  D/dalvikvm(  149): -------- end of chaining cells (0x0034)
  D/dalvikvm(  149): End Ljava/lang/String;hashCode, 1 Dalvik instructions
  E/Trace   (  213): error opening trace file: No such file or directory (2)
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for isHighSurrogate, offset 0
  D/dalvikvm(  149): 0x45ca79f4: 0x0014 const v0, (#55296), (#0)
  D/dalvikvm(  149): 0x45ca79fa: 0x0036 if-gt v0, v1, (+9)
  D/dalvikvm(  149): TRACEINFO (12): 0x45ca79f4 Ljava/lang/Character;isHighSurrogate.(C)Z 0 5 of 14, 6 blocks
  D/dalvikvm(  149): Compiling Ljava/lang/Character; isHighSurrogate
  D/dalvikvm(  149): 14 insns
  D/dalvikvm(  149): 6 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0000 - 0000 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0000)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0000 - 0003)
  D/dalvikvm(  149):   Taken branch: block 3 (000c)
  D/dalvikvm(  149):   Fallthrough : block 2 (0005)
  D/dalvikvm(  149): Block 2 (Normal Chaining Cell) (insn 0005 - 0005 empty)
  D/dalvikvm(  149): Block 3 (Normal Chaining Cell) (insn 000c - 000c empty)
  D/dalvikvm(  149): Block 4 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 5 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45ca79f4
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d4874d0
  D/dalvikvm(  149): total size is 80 bytes
  D/dalvikvm(  149): 0x4d4874d0 (0000): data    0xc050(49232)
  D/dalvikvm(  149): 0x4d4874d2 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d4874d4 (0004): data    0x0034(52)
  D/dalvikvm(  149): 0x4d4874d6 (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d4874da (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d4874dc (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d4874de (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0000
  D/dalvikvm(  149): L0x4ac29f94:
  D/dalvikvm(  149): -------- dalvik offset: 0x0000 @ const v0, (#55296), (#0)
  D/dalvikvm(  149): 0x4d4874e0 (0010): ldr     r1, [r5, #4]
  D/dalvikvm(  149): 0x4d4874e2 (0012): mov     r0, #55296 [0xd800]
  D/dalvikvm(  149): -------- dalvik offset: 0x0003 @ if-gt v0, v1, (+9)
  D/dalvikvm(  149): 0x4d4874e6 (0016): cmp     r0, r1
  D/dalvikvm(  149): 0x4d4874e8 (0018): str     r0, [r5, #0]
  D/dalvikvm(  149): 0x4d4874ea (001a): bgt     0x4d4874fc (L0x4ac2a014)
  D/dalvikvm(  149): 0x4d4874ee (001e): b       0x4d4874f0 (L0x4ac29fd4)
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d4874f0 (0020): .align4
  D/dalvikvm(  149): L0x4ac29fd4:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x0005
  D/dalvikvm(  149): 0x4d4874f0 (0020): b       0x4d4874f4 (L0x4ac2a710)
  D/dalvikvm(  149): 0x4d4874f2 (0022): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a710:
  D/dalvikvm(  149): 0x4d4874f4 (0024): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d4874f6 (0026): blx     r0
  D/dalvikvm(  149): 0x4d4874f8 (0028): data    0x79fe(31230)
  D/dalvikvm(  149): 0x4d4874fa (002a): data    0x45ca(17866)
  D/dalvikvm(  149): 0x4d4874fc (002c): .align4
  D/dalvikvm(  149): L0x4ac2a014:
  D/dalvikvm(  149): -------- chaining cell (normal): 0x000c
  D/dalvikvm(  149): 0x4d4874fc (002c): b       0x4d487500 (L0x4ac2a910)
  D/dalvikvm(  149): 0x4d4874fe (002e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2a910:
  D/dalvikvm(  149): 0x4d487500 (0030): ldr     r0, [r6, #100]
  D/dalvikvm(  149): 0x4d487502 (0032): blx     r0
  D/dalvikvm(  149): 0x4d487504 (0034): data    0x7a0c(31244)
  D/dalvikvm(  149): 0x4d487506 (0036): data    0x45ca(17866)
  D/dalvikvm(  149): -------- end of chaining cells (0x0038)
  D/dalvikvm(  149): End Ljava/lang/Character;isHighSurrogate, 2 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for upperIndex, offset 0x12
  D/dalvikvm(  149): 0x45ca5bc4: 0x0001 move v1, v0, (#0)
  D/dalvikvm(  149): 0x45ca5bc6: 0x000f return v1, (#0), (#0)
  D/dalvikvm(  149): TRACEINFO (13): 0x45ca5ba0 Ljava/lang/CaseMapper;upperIndex.(I)I 0x12 2 of 114, 4 blocks
  D/dalvikvm(  149): Compiling Ljava/lang/CaseMapper; upperIndex
  D/dalvikvm(  149): 114 insns
  D/dalvikvm(  149): 4 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0012 - 0012 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0012)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0012 - 0013)
  D/dalvikvm(  149): Block 2 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 3 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45ca5bc4
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487520
  D/dalvikvm(  149): total size is 68 bytes
  D/dalvikvm(  149): 0x4d487520 (0000): data    0xc054(49236)
  D/dalvikvm(  149): 0x4d487522 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487524 (0004): data    0x0024(36)
  D/dalvikvm(  149): 0x4d487526 (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48752a (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d48752c (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d48752e (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0012
  D/dalvikvm(  149): L0x4ac29f34:
  D/dalvikvm(  149): -------- dalvik offset: 0x0012 @ move v1, v0, (#0)
  D/dalvikvm(  149): 0x4d487530 (0010): ldr     r0, [r5, #0]
  D/dalvikvm(  149): -------- dalvik offset: 0x0013 @ return v1, (#0), (#0)
  D/dalvikvm(  149): 0x4d487532 (0012): movs    r1, r0
  D/dalvikvm(  149): 0x4d487534 (0014): str     r1, [r6, #16]
  D/dalvikvm(  149): 0x4d487536 (0016): str     r0, [r5, #4]
  D/dalvikvm(  149): 0x4d487538 (0018): blx_1   0x4d486028
  D/dalvikvm(  149): 0x4d48753a (001a): blx_2   see above
  D/dalvikvm(  149): 0x4d48753c (001c): b       0x4d487540 (L0x4ac2a4ec)
  D/dalvikvm(  149): 0x4d48753e (001e): undefined
  D/dalvikvm(  149): L0x4ac2a4ec:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45ca5bc6 @ +0x0013
  D/dalvikvm(  149): 0x4d487540 (0020): ldr     r0, [r15pc, #28]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d487544 (0024): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d487546 (0026): blx     r1
  D/dalvikvm(  149): -------- end of chaining cells (0x0028)
  D/dalvikvm(  149): 0x4d487560 (0040): .word (0x45ca5bc6)
  D/dalvikvm(  149): End Ljava/lang/CaseMapper;upperIndex, 2 Dalvik instructions
  D/dalvikvm(  149): --------
  D/dalvikvm(  149): Compiler: Building trace for toUpperCase, offset 0x43
  D/dalvikvm(  149): 0x45ca59f2: 0x0071 invoke-static v2
  D/dalvikvm(  149): GC_CONCURRENT freed 375K, 5% free 7760K/8168K, paused 14ms+64ms, total 381ms
  D/dalvikvm(  149): WAIT_FOR_CONCURRENT_GC blocked 122ms
  D/dalvikvm(  149): 0x45ca59f8: 0x000a move-result v6, (#0), (#0)
  D/dalvikvm(  149): TRACEINFO (14): 0x45ca596c Ljava/lang/CaseMapper;toUpperCase.(Ljava/util/Locale;Ljava/lang/String;[CII)Ljava/lang/String; 0x43 4 of 273, 7 blocks
  D/dalvikvm(  149): Compiling Ljava/lang/CaseMapper; toUpperCase
  D/dalvikvm(  149): 273 insns
  D/dalvikvm(  149): 7 blocks in total
  D/dalvikvm(  149): Block 0 (Entry Block) (insn 0043 - 0043 empty)
  D/dalvikvm(  149):   Fallthrough : block 1 (0043)
  D/dalvikvm(  149): Block 1 (Code Block) (insn 0043 - 0043)
  D/dalvikvm(  149):   Taken branch: block 3 (0000)
  D/dalvikvm(  149):   Fallthrough : block 2 (0046)
  D/dalvikvm(  149): Block 2 (Code Block) (insn 0046 - 0046)
  D/dalvikvm(  149):   Fallthrough : block 4 (0047)
  D/dalvikvm(  149): Block 3 (Singleton Chaining Cell) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 4 (Hot Chaining Cell) (insn 0047 - 0047 empty)
  D/dalvikvm(  149): Block 5 (PC Reconstruction) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Block 6 (Exception Handling) (insn 0000 - 0000 empty)
  D/dalvikvm(  149): Trace Dalvik PC: 0x45ca59f2
  D/dalvikvm(  149): Dumping LIR insns
  D/dalvikvm(  149): installed code is at 0x4d487564
  D/dalvikvm(  149): total size is 152 bytes
  D/dalvikvm(  149): 0x4d487564 (0000): data    0xc058(49240)
  D/dalvikvm(  149): 0x4d487566 (0002): data    0x4ac2(19138)
  D/dalvikvm(  149): 0x4d487568 (0004): data    0x0054(84)
  D/dalvikvm(  149): 0x4d48756a (0006): ldr     r0, [r15pc, -#8]
  D/dalvikvm(  149): 0x4d48756e (000a): ldr     r1, [r0, #0]
  D/dalvikvm(  149): 0x4d487570 (000c): adds    r1, r1, #1
  D/dalvikvm(  149): 0x4d487572 (000e): str     r1, [r0, #0]
  D/dalvikvm(  149): -------- entry offset: 0x0043
  D/dalvikvm(  149): L0x4ac2a30c:
  D/dalvikvm(  149): -------- dalvik offset: 0x0043 @ invoke-static v2
  D/dalvikvm(  149): 0x4d487574 (0010): ldr     r0, [r5, #8]
  D/dalvikvm(  149): 0x4d487576 (0012): sub     r7,r5,#24
  D/dalvikvm(  149): -------- BARRIER
  D/dalvikvm(  149): 0x4d48757a (0016): stmia   r7, <r0>
  D/dalvikvm(  149): -------- BARRIER
  D/dalvikvm(  149): 0x4d48757c (0018): ldr     r0, [r15pc, #120]
  D/dalvikvm(  149): 0x4d487580 (001c): add     r1, pc, #16
  D/dalvikvm(  149): 0x4d487582 (001e): ldr     r4, [r15pc, #112]
  D/dalvikvm(  149): 0x4d487586 (0022): movs    r7, #5
  D/dalvikvm(  149): 0x4d487588 (0024): movs    r2, #0
  D/dalvikvm(  149): 0x4d48758a (0026): blx_1   0x4d486110
  D/dalvikvm(  149): 0x4d48758c (0028): blx_2   see above
  D/dalvikvm(  149): 0x4d48758e (002a): b       0x4d4875b0 (L0x4ac2a38c)
  D/dalvikvm(  149): 0x4d487590 (002c): b       0x4d48759c (L0x4ac2ab14)
  D/dalvikvm(  149): 0x4d487592 (002e): .align4
  D/dalvikvm(  149): L0x4ac2a34c:
  D/dalvikvm(  149): -------- dalvik offset: 0x0046 @ move-result v6, (#0), (#0)
  D/dalvikvm(  149): 0x4d487594 (0030): ldr     r0, [r6, #16]
  D/dalvikvm(  149): 0x4d487596 (0032): str     r0, [r5, #24]
  D/dalvikvm(  149): 0x4d487598 (0034): b       0x4d4875a4 (L0x4ac2a3cc)
  D/dalvikvm(  149): 0x4d48759a (0036): undefined
  D/dalvikvm(  149): L0x4ac2ab14:
  D/dalvikvm(  149): -------- reconstruct dalvik PC : 0x45ca59f2 @ +0x0043
  D/dalvikvm(  149): 0x4d48759c (0038): ldr     r0, [r15pc, #84]
  D/dalvikvm(  149): Exception_Handling:
  D/dalvikvm(  149): 0x4d4875a0 (003c): ldr     r1, [r6, #108]
  D/dalvikvm(  149): 0x4d4875a2 (003e): blx     r1
  D/dalvikvm(  149): 0x4d4875a4 (0040): .align4
  D/dalvikvm(  149): L0x4ac2a3cc:
  D/dalvikvm(  149): -------- chaining cell (hot): 0x0047
  D/dalvikvm(  149): 0x4d4875a4 (0040): b       0x4d4875a8 (L0x4ac2af00)
  D/dalvikvm(  149): 0x4d4875a6 (0042): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2af00:
  D/dalvikvm(  149): 0x4d4875a8 (0044): ldr     r0, [r6, #116]
  D/dalvikvm(  149): 0x4d4875aa (0046): blx     r0
  D/dalvikvm(  149): 0x4d4875ac (0048): data    0x59fa(23034)
  D/dalvikvm(  149): 0x4d4875ae (004a): data    0x45ca(17866)
  D/dalvikvm(  149): 0x4d4875b0 (004c): .align4
  D/dalvikvm(  149): L0x4ac2a38c:
  D/dalvikvm(  149): -------- chaining cell (invoke singleton): Ljava/lang/CaseMapper;upperIndex/0x45ca5ba0
  D/dalvikvm(  149): 0x4d4875b0 (004c): b       0x4d4875b4 (L0x4ac2b100)
  D/dalvikvm(  149): 0x4d4875b2 (004e): orrs    r0, r0
  D/dalvikvm(  149): L0x4ac2b100:
  D/dalvikvm(  149): 0x4d4875b4 (0050): ldr     r0, [r6, #116]
  D/dalvikvm(  149): 0x4d4875b6 (0052): blx     r0
  D/dalvikvm(  149): 0x4d4875b8 (0054): data    0x5ba0(23456)
  D/dalvikvm(  149): 0x4d4875ba (0056): data    0x45ca(17866)
  D/dalvikvm(  149): -------- end of chaining cells (0x0058)




