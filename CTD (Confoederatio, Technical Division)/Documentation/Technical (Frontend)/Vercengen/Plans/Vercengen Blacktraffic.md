**Blacktraffic.AgentBrowser**:
- static getBrowser(arg0_key)
- static getBrowsers()
**Blacktraffic.AgentBrowserPuppeteer**: (default instance)
- arg1_options:
	- chrome_binary_path: string
	- debug_console: boolean - False by default, determines if captureConsoleToChannel() is invoked automatically
	- debugging_port: number (uses --remote-debugging-port=0 if not provided)
	- user_data_folder: string - Refers to a Chrome profile necessary for spoofing
- **Methods:**
- captureConsoleToChannel(arg0_channel_key) - 'console' by default if not provided
- close() - Closes the mounted browser
- closeTab(arg0_tab)
- closeUserTabs() - Closes all tabs that do not have an `.id` assigned to them.
- focusTab(arg0_tab)
- getTab(arg0_tab_key)
- getTabs() | Array\<Tab\>
- injectScript(arg0_tab, arg1_function)
- injectScriptOnload(arg0_tab, arg1_function)
- open() - Opens a browser if it the constructor browser has been unmounted
- openTab(arg0_tab)
- reloadTab(arg0_tab)
- tabExists(arg0_tab)
- setHeadless(arg0_boolean)
- waitForStableContent(arg0_tab, arg1_selector, arg2_interval)
**Blacktraffic.AgentBrowserSelenium:**
- **Methods:**
- captureConsoleToChannel(arg0_channel_key) - 'console' by default if not provided
- close() - Closes the mounted browser
- closeTab(arg0_tab)
- closeUserTabs() - Closes all tabs that do not have an `.id` assigned to them.
- focusTab(arg0_tab)
- getTab(arg0_tab_key)
- getTabs() | Array\<Tab\>
- injectScript(arg0_tab, arg1_function)
- injectScriptOnload(arg0_tab, arg1_function)
- open() - Opens a browser if it the constructor browser has been unmounted
- openTab(arg0_tab)
- reloadTab(arg0_tab)
- tabExists(arg0_tab)
- setHeadless(arg0_boolean)
- waitForStableContent(arg0_tab, arg1_selector, arg2_interval)

==Merge CURL methods with the contracts in Blacktraffic.AgentBrowserPuppeteer/Blacktraffic.AgentBrowserSelenium==.