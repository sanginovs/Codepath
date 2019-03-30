# Summary

* Honeypot(s) deployed:
  * Dionea
  * Dionea with HTTP
  * wordpot

* Any Issues you encountered
  * At the beginning, I was unable to access MHN-admin using its public IP on Google Cloud. Then, I figured that i was using HTTPS to access the mhn-admin. I had to use http because https was not configured on Google cloud server. So, I had to speccify http protocol in the url.
  * Another issue I ran is that MHN-admin did not capture any attacks from my second and third honeypot.
  * Finally, my first honeypot was attacked more than 2000 times but MHN-admin did not capture any malware or payload. Maybe, i had to do some extra configuration.  

* A Summary of the data collected: number of attacks, number of malware samples, etc.
   * mhn-honeypot-1 (Dionea)
	* Attacks: 2245
        * Duration live: 12 hours
        * Protocols: pcap, smbd, SipCall, SipSession, ftpd, httpd, mysqldb
   
