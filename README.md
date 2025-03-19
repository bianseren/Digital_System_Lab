# Digital_System_Lab

// Verilog Command List - Keywords and Functions

// 1. Data Types
type wire;       // Represents a combinational signal
type reg;        // Stores values, used in procedural blocks
type integer;    // Used for loop counters and calculations
type real;       // Floating-point numbers (not synthesizable)
type parameter;  // Defines constant values

// 2. Operators
// Arithmetic Operators
assign sum = a + b;  // Addition
assign diff = a - b; // Subtraction
assign prod = a * b; // Multiplication
assign quot = a / b; // Division (not synthesizable for hardware)

// Bitwise Operators
assign and_out = a & b; // AND operation
assign or_out  = a | b; // OR operation
assign xor_out = a ^ b; // XOR operation
assign not_out = ~a;    // NOT operation

// Logical Operators (return boolean values)
assign logic_and = a && b; // Logical AND
assign logic_or  = a || b; // Logical OR
assign logic_not = !a;     // Logical NOT

// Comparison Operators
assign eq  = (a == b);  // Equal
assign neq = (a != b);  // Not equal
assign lt  = (a < b);   // Less than
assign gt  = (a > b);   // Greater than
assign leq = (a <= b);  // Less than or equal to
assign geq = (a >= b);  // Greater than or equal to

// Shift Operators
assign shift_left  = a << 2; // Shift left by 2 bits
assign shift_right = a >> 2; // Shift right by 2 bits

// Reduction Operators
assign and_reduce = &a; // AND all bits of 'a'
assign or_reduce  = |a; // OR all bits of 'a'
assign xor_reduce = ^a; // XOR all bits of 'a'

// 3. Control Statements
if (a > b) begin
    assign result = a;
end else begin
    assign result = b;
end

// 4. Module Definition
module example (input wire clk, output reg out);
    always @(posedge clk) begin
        out <= ~out;
    end
endmodule

// 5. Simulation & Debugging
initial begin
    $display("Simulation starts");
    $monitor("Time: %0t | Signal: %b", $time, out);
end
