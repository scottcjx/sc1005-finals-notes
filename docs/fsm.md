# Finite State Machine

### Sequence Diagram


### Verilog implementation

Using a [combinational circuit](./verilog#combinational) + [switch case](./verilog#switch-case).

``` v
always @ *
begin
    case (varName)
    4'b0001: // code
    4'b0002: // code
    default: // code
    endcase
end
```
