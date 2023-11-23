# Common Circuits

## Gates
Gate level `primitives`: gates provided:
`and, nand, or, nor, not, xor, xnor`

``` v
// the (single) output is always the first input
and(outp, x, y);
or(outp, a, b, c, d);

// primitive gate allows more than 2 inputs
```

## Complex Circuits

### Latches

#### SR Latch
Set-Reset latch

$(set \ \&\& \ output == low) \rightarrow output = high$

$(reset \ \&\& \ output == high) \rightarrow output = low$

#### D Latch

$ (switch \ \& \& \ output == low) -> output = high $

$ (switch \ \& \& \ output == high) -> output = low $

> eqiv c code: `if (switch) output = !output`

### Flip Flops
Flip-flops are `clock` enabled [latches](#latches)

#### D Flip Flop
on `clock` edge, `output Q` inherits `input D`.
refer to [D latch](#d-latch)

#### J-K Flip Flop
on `clock` edge:

$ (J \ \& \& \ \neg K) \rightarrow Q = 1 $

$ (\neg J \ \& \& \ K) \rightarrow Q = 0 $

$ ( J \ \& \& \ K) \rightarrow Q = \neg Q $

#### T Flip Flop
on `clock` edge:

$ (T == high) \rightarrow Q = \neg Q $

### Decoder

### Multiplexer (Mux)


