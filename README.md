# CCNA networking concepts, including key terms, protocols, and topologies. 

## Basic Switch and End Device Configuration
### IOS Navigation

1- Primary Command Modes
- **User EXEC Mode:** This mode has limited capabilities but is useful for basic operations. It allows only a limited number of basic monitoring commands but does not allow the execution of any commands that might change the configuration of the device. The user EXEC mode is identified by the CLI prompt that ends with the `>` symbol. <br>
    `Switch>` <br>
    `Router>`

- **Privileged EXEC Mode:** To execute configuration commands, a network administrator must access privileged EXEC mode. Higher configuration modes, like global configuration mode, can only be reached from privileged EXEC mode. The privileged EXEC mode can be identified by the prompt ending with the `#` symbol.<br>
    `Switch#` <br>
    `Router#`

2- Configuration Mode and Subconfiguration Modes <br>
To configure the device, the user must enter global configuration mode, which is commonly called global config mode.

From global config mode, CLI configuration changes are made that affect the operation of the device as a whole. Global configuration mode is identified by a prompt that ends with `(config)#` after the device name, such as `Switch(config)#`.

Global configuration mode is accessed before other specific configuration modes. From global config mode, the user can enter different subconfiguration modes. Each of these modes allows the configuration of a particular part or function of the IOS device. Two common subconfiguration modes include:

- Line Configuration Mode - Used to configure console, SSH, Telnet, or AUX access.
- Interface Configuration Mode - Used to configure a switch port or router network interface.

When the CLI is used, the mode is identified by the command-line prompt that is unique to that mode. By default, every prompt begins with the device name. Following the name, the remainder of the prompt indicates the mode. For example, the default prompt for line configuration mode is `Switch(config-line)#` and the default prompt for interface configuration mode is `Switch(config-if)#`.

3- Navigate Between IOS Modes <br>
Various commands are used to move in and out of command prompts. To move from user EXEC mode to privileged EXEC mode, use the `enable` command. Use the `disable` privileged EXEC mode command to return to user EXEC mode.

To move in and out of global configuration mode, use the `configure terminal` privileged EXEC mode command. To return to the privileged EXEC mode, enter `exit`.

There are many different subconfiguration modes. For example, to enter line subconfiguration mode, you use the line command followed by the management line type and number you wish to access. Use the `exit` command to exit a subconfiguration mode and return to global configuration mode.

To move from any subconfiguration mode to the privileged EXEC mode, enter the `end` command or enter the key combination `Ctrl+Z`.

You can also move directly from one subconfiguration mode `Switch(config-if)` to another.

```
Switch>
Switch>enable
Switch#config
Switch#configure terminal 
Switch(config)#interface fastEthernet 0/5
Switch(config-if)#interface vlan 1
Switch(config-if)#end
Switch#disable
Switch>
```