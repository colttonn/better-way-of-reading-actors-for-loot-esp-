# better way of reading pickup entities
I still see too many pastes using fname too identify loot entities that´s why im gonna show
a better method which takes less reads then fname to get loot entites trough actors.

The offset im talking about is SimulatingTooLongLength inside the AFortPickup Class.
To use it, loop trough actors and then read the offset ( current one is 0x2C8 ) as a float and after that
you check if the value is between 0 and 100. After that you normally read the PrimaryItemPickupEntry etc, 
i wont show the full code, just an example on how to read it if someone does not understand the text.

 float SimulatingTooLongLength = memory->read<float>(actor + 0x2C8);
 
if (SimulatingTooLongLength >= 0.f && SimulatingTooLongLength <= 100.f) {
   //the usuall reading logic (PrimaryPickupItemEntry etc)
 }

