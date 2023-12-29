emmc + qspi_controller : this is a mix project for emmc_ht3 daughter card  
in qspi part, this daughter card is using Winbone W25Q256JW nor flash as the external qspi flash device  

this qspi contoller support 4 input command:  
1. write_en: 24bit programable address: "addr" and 1 word programable data : "data"  will be asserted by Page Program instruction  
2. read_en: Read Data instruction will give the data to "read_data" from the address relative to "addr"
3. readid_en: JEDEC instruction assigned Manufacturer ID byte for Winbond (EFh) and two Device ID bytes, Memory Type (ID15-ID8) and Capacity (ID7-ID0) are th Manufacturer ID (EFh) from flash device to "read_data"  
4. erase_en: The Erase instruction sets all memory within a specified sector (4K-bytes) to the erased state

     following is the state machine of the qspi controller
![alt text](https://github.com/joshuahwfwEE/emmc-qspi_controller/blob/main/qspi_controller_state_machine.png?raw=true)
   
