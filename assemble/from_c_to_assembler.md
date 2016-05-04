# from c to assembler

gccでコンパイルするときに`-S`オプションを付ける

- test.c

```
int main(){
  int x = 123;
  /* before if */
  if (x == 456) {
    /* in if */
  }
  /* after if */
}
```

があったとして、


```
$ gcc -S test.c
```

を実行すると`test.s`が生成される

- test.s

```
	.section	__TEXT,__text,regular,pure_instructions
	.macosx_version_min 10, 11
	.globl	_main
	.align	4, 0x90
_main:                                  ## @main
	.cfi_startproc
## BB#0:
	pushq	%rbp
Ltmp0:
	.cfi_def_cfa_offset 16
Ltmp1:
	.cfi_offset %rbp, -16
	movq	%rsp, %rbp
Ltmp2:
	.cfi_def_cfa_register %rbp
	movl	$0, -4(%rbp)
	movl	$123, -8(%rbp)
	cmpl	$456, -8(%rbp)          ## imm = 0x1C8
	jne	LBB0_2
## BB#1:
	jmp	LBB0_2
LBB0_2:
	movl	-4(%rbp), %eax
	popq	%rbp
	retq
	.cfi_endproc


.subsections_via_symbols
```
