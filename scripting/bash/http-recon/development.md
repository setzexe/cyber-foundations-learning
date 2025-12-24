# Development & Notes

## 1.0 

The execution flow of the tool should flow out simply like this:

- User runs tool
- Tool validates input 
- Tool checks reachability
- Tool makes HTTP request
- Tool prints results
- Tool exits

For now, very simple. Nothing complex. We will extend upon this tool as we learn more about it.

For the input interface, it could be as simple as just running the script and having the first argument be the wanted target. Along with this is validating that there actually is an argument, but this is as simple as just a -z check for the first argument. If this "if" condition passes, we echo the correct usage and exit the script.

We must check reachability before we actually grab the HTTP headers. To do this, we utilize *ping* to check reachability. 

- Ping *might* not work depending on the environment. As I work on this via hotel wifi, ICMP packets are blocked. This allows sites to still be accessible, but not reachable via ICMP. This would be fine for home wifi's, but many private networks might catch a similar issue. For this reason, we will not exit the script if ping doesn't work. Rather, we'll just echo that ICMP might be blocked.

Once that is settled, we use *curl* to access the headers of the target. *curl* is very common is cyber. For now, only accessing the headers is fine. These headers can reveal server software, frameworks, proxies, and misconfigurations.

