# Freeswitch cheat-sheet:

1. update dialplan

		reloadxml
2. update one module

		reload mod_modname

3. update sip_profile

		sofia profile external restart
		sofia profile external register 010

4. add new extension
    
   	touch /etc/freeswitch/directory/default/10xx.xml
   	
5. fxs_cli

	enter cli for freeswitch
6. /exit
	
	quit from cli
	
7. Api and application

	originate
	bridge
	commands:
	sofia status
	sofia status profile internal/external
	sofia status profile internal reg	
	show codec: 显示编码
	
8. profile
	default (5060)
	public  (5080)
	
	
9. dialplan
	
   * default
   * public
   		* destination_number='xxxx'
   		* for inbound call which bridge to callcenter
   
10. callcenter
		* queue
		* tiers
		* agents
		* reload mod_callcenter
11. vars.xml
	env vars are defined in this file like sip port, extension password...

12. start freeswitch in background

		freeswitch -nc
		
		
		