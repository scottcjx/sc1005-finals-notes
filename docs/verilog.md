# Verilog

## Contents
- [Modules](#modules)
- [Behavioral Verilog](#behavioual-verilog)
- [Switch-Case](#switch-case)
- [Finate State Machines (FSM)](./fsm)
- [Common Circuits](./circuits)


### Modules
#### Declaring a module
``` v
module nameOfModule(
    input nameOfInputInline1, nameOfInputInline2,
    input nameOfInputSecondLine,
    output nameOfOutput1
);

// code

endmodule
```

#### Instantiation of a module
Module I want to use in my other module
``` v
module mySimpleCircuit(
    input x, y,
    output z
);
endmodule
```

Main module
``` v
module myComplexCircuit(
    input a, b,
    output outp
);

// ordered instantiation
mySimpleCircuit modAlias1(b, a, outp);

// named instantiation
mySimpleCircuit modAlias2(.x(b), .y(a), .z(outp));

endmodule
```

## Structural Verilog

#### Assign
Continuous: They will be permanent

#### Vectors
Multi-bit or bus signals that uses more than 1 wire.

``` v
// MSB -> LSB
wire [3:0] x; // 4 bit bus x
```

#### Numbers
Number Literals
``` v
// Number literal
// <size>'<radix><value>
// size: size in BITS
/* radix: 
    b for binary
    o for octal
    d for decimal
    h for hexa
*/

4'd4    // decimal number 4
4'b0100 // binary eqiv of 4 (decimal)
4'hA    // hex eqiv of 16 (decimal)
1'b1    // single bit 1
```

Number Concatinations
``` v
wire [3:0] a, b;
wire [7:0] y;
assign y = {a, b};

assign b = {a[3:0], 4’b0000}; // b is 8 bit
```

#### Parameters
Local Variables

``` v
parameter x = 4'b0011;  // local var x in module
```

## Behavioual Verilog

Always Statements:
``` v
always @ ( /* sensitivity list */ )
begin
    // procedural statements
end
```

\* can **never** use an `assign` keyword inside an always block.

\* signals assigned inside always block must be of type `reg`

Combinational vs Sequential Always Statements

|A|Combinational|Sequential|
|:--|:--:|:--:|
|execution|propogation delay|clk pulse|
||faster|predictable|
|sequence of code|line by line|same time|
|assignments|=|<=|
|sequence of assignment matter|YES|NO|
|creates a latch + register|NO|YES|
|usually handles RST|NO|YES|

|Statement|T/F|
|:-|:-:|
|multiple circuits in same module is allowed|T|
|sequential and combinational in same module is allowed|T|


#### Combinational

``` v
always @ *
begin
    // code
end
```

#### Sequential

``` v
always @ (posedge nameOfClk)
begin
    // code
end
```

### Switch Case

``` v
case (varName)
    numberEquilaventVar: // code
    2'b11: // code
endcase
```
