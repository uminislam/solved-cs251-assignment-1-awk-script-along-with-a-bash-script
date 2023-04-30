Download Link: https://assignmentchef.com/product/solved-cs251-assignment-1-awk-script-along-with-a-bash-script
<br>
Given a directory which contains sub-directories and C fiess write an AWK script along with a bash script to print the total number of lines of comments and totai number of strings in the whole directory. The bash script shouid get aii .c fies recursiveiy and the AWK script shouid parse them. You can assume aii the C fies are error-free and pre-processed. Ex:-

dir   |-inc

|-soiution.h

|-src

|-main.c      |-soiution.c

<h1>solution.c</h1>

// This is a single line comment

/* This is a multi-line comment */

/* This is another    multi-line “comment”    considered as 4 lines

*/

#include &lt;solution.h&gt; int solution(void)

{

char *s = “try combinations of strings and /*comments*/ too”;     return 0;

}

<h1>main.c</h1>

#include &lt;stdio.h&gt; int main(void)

{

// The following output is the actual solution !!!     printf(“7 lines of comments
”);     printf(“3 quoted strings
”);

return 0; }

Expianation:-

The fie <em>solution.c</em> contains 1 string and 6 iines of comments. The <em>main.c</em> fie contains 1 comment and 2 strings and thus the output for the whoie directory wiii be 3 strings and 7 iines of comments.

<strong>Q2. </strong>

Write an AWK script which accepts packet capture iog as input. The packet capture iog contains information about packets transferred across the network. In this assignments we are interested to fnd out packets transmitted through TCP connection. A TCP connection is identifed by a four tupie &lt;source IPs source ports destination IP and destination port&gt;. The data is transferred in both directions and identifed by the sequence number. Consider the foiiowing exampie packet capture iog.

00:58:45.452688 IP 74.125.130.189.443 &gt; 172.25.92.26.48288: Fiags [P.]s seq 1095791942:1095792002s ack 2430684857s win 258s options [nopsnopsTS vai 3399350415 ecr 26537982]s iength 60

In this packets the reievant portions for this assignment are given beiow.

timestamp=00:58:45.452688

Sender IP = 74.125.130.189s Sender Port = 443

Receiver IP = 172.25.92.26s Receiver PORT = 48288

Data sequence start = 1095791942s end = 1095792002s where every data byte is assigned a unique sequence number.

For a given packet capture iog fie print the foiiowing output for each connections.

Connection  (A = IP:PORTs B=IP:PORT) ————————————

A–&gt;B

#of packets (aii)    #of data packets     #Data (bytes)      #Retransmitted (bytes) Throughput (bytes/sec)

B–&gt;A

#of packets (aii)    #of data packets     #Data (bytes)      #Retransmitted (bytes)

Throughput (bytes/sec)




Note:

<ol>

 <li>Aii packets transferred may not carry data (some of them are acknowiedgements).</li>

 <li>Retransmission events can be captured by comparing sequence numbers of packet withpreviousiy transmitted packets.</li>

 <li>The <em>throughput</em> is the unique number of bytes deiivered per second (bytes/sec)s known as “goodput” in Computer Networks.</li>

 <li>Attached archive contains packet capture iogs (in the above format in .txt fies) and the rawpackets (fies with .pcap extension) which can be opened using Wireshark (GUI) or tcpdump (command iine).</li>

</ol>