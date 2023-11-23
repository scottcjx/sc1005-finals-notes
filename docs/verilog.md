# Verilog

## Contents
- [Modules](#modules)
- [Types of Circuits](#types-of-circuits)
- [Switch-Case](#switch-case)
- [Finate State Machines (FSM)](./fsm)
- [Common Circuits](./circuits)


### Modules

Structure of declaring a module:

``` v
module nameOfModule(
    input nameOfInputInline1, nameOfInputInline2,
    input nameOfInputSecondLine,
    output nameOfOutput1
);

// code

endmodule
```

### Variables



### Types of Circuits

Combinational vs Sequential

|A|Combinational|Sequential|
|:--|:--:|:--:|
|execution|propogation delay|clk pulse|
||faster|predictable|
|sequence of code|line by line|same time|
|assignments|assign|<=|
|sequence of assignment matter|YES|NO|
|creates a latch + register|NO|YES|
|usually handles RST|NO|YES|

<br>

---

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
    endcase
```


