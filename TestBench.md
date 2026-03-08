# TESTBENCH
```verilog
`timescale 1ns / 1ps

module testbench;

reg clk;
reg reset;
reg [15:0] datain;

wire spi_cs_l;
wire spi_sclk;
wire spi_data;
wire [4:0] counter;

spi_state dut(
    .clk(clk),
    .reset(reset), 
    .datain(datain),
    .spi_cs_l(spi_cs_l),
    .spi_sclk(spi_sclk),
    .spi_data(spi_data),
    .counter(counter)
);


// Clock generation
initial begin
    clk = 0;
    forever #5 clk = ~clk;   // 10ns clock period
end


// Stimulus
initial begin
    reset = 1;
    datain = 16'h0000;

    #20 reset = 0;

    #50  datain = 16'hA569;
    #200 datain = 16'h2563;
    #200 datain = 16'h9B63;
    #200 datain = 16'h6A61;
    #200 datain = 16'hA265;
    #200 datain = 16'h7564;

    #500 $finish;
end

endmodule
```
