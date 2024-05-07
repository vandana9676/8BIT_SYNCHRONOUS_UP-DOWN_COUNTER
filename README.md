# 8BIT_SYNCHRONOUS_UP-DOWN_COUNTER
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/e1af47bf-e77f-446e-9fe0-e0ca3d1a7cfd)
# Here is a diagram showing the circuit in the "up" counting mode
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/8a6dd34b-5226-4d93-9bff-d87ab85aeabc)
# Here, shown in the "down" counting mode
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/9a30ebd6-6692-48d0-b64b-41b896d6de4a)
## VHDL CODE:
library IEEE;

use IEEE.STD_LOGIC_1164.ALL;

use IEEE.STD_LOGIC_ARITH.ALL;

use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity updn is

    Port ( clk : in STD_LOGIC;
    
           clr : in STD_LOGIC;
           
           updown : in std_logic;
           
           count : out std_logic_vector (7 downto 0));

end updn;

architecture Behavioral of updn is

signal tmp : std_logic_vector(7 downto 0);


begin

process

begin

wait until clk'event and clk ='1';

if (clr ='1') then

tmp<="00000000";

elsif (updown ='1') then

tmp <= tmp + 1;

else

tmp <= tmp - 1;


end if;

count <= tmp;

end process;

end Behavioral;
## OUTPUT:
![image](https://github.com/vandana9676/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/165563035/7388f806-51cf-450b-996d-3bf1d3ffae03)
