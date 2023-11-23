# Finite State Machine

### Sequence Diagram


### Verilog implementation

Using a [combinational circuit](./verilog#combinational) + [switch case](./verilog#switch-case).

``` v
module myStateMachine(
    input rst, clk,
    output state
);

// define states (just like c enum)
// as parameters, switch case w it
parameter stateName1 = 2'b01;
parameter stateName2 = 2'b10;
parameter stateName3 = 2'b11;

reg [1:0] nxt_state, curr_state;

always @ (posedge)
begin
    // handle reset input
    if (rst)
        curr_state <= stateName1;
    else
        curr_state <= nxt_state;
end

always @ *
begin
    case (varName)
    stateName1: // code
    stateName2: // code
    stateName3: // code
    default: // code
    endcase
end
```
