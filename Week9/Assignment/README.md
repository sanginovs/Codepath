# Summary

* Honeypot(s) deployed:
  * Dionea
  * Dionea with HTTP
  * wordpot
  ![deployed](https://raw.githubusercontent.com/sanginovs/Codepath/master/Week9/Assignment/honeypots.png)
   
* Any Issues you encountered
  * At the beginning, I was unable to access MHN-admin using its public IP on Google Cloud. Then, I figured that i was using HTTPS to access the mhn-admin. I had to use http because https was not configured on Google cloud server. So, I had to speccify http protocol in the url.
  * Another issue I ran is that MHN-admin did not capture any attacks from my second and third honeypot.
  * Finally, my first honeypot was attacked more than 2000 times but MHN-admin did not capture any malware or payload. Maybe, i had to do some extra configuration.  

* A Summary of the data collected: number of attacks, number of malware samples, etc.
   * mhn-honeypot-1 (Dionea)
	* Attacks: 2245 days
        * Duration live: 3 days
        * Protocols: pcap, smbd, SipCall, SipSession, ftpd, httpd, mysqldb
        * ![attacks](https://github.com/sanginovs/Codepath/blob/master/Week9/Assignment/attacks.png)
   * mhn-honeypot-2 (Dionea with HTTP)
        * Attacks: 0 (Issue)
        * Duration live: 1 hour
   * mhn-honeypot-3 (Wordpot)
       * Attacks: 0
   * Any unresolved questions raised by the data collected: 
       * Question: Why did it not collect malware?   
  
