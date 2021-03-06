# What's My Name?

__PROBLEM__

Say my name, say [my name](https://2018shell.picoctf.com/static/311cab88f8331b8cd1285ae0d90a43f1/myname.pcap).

__HINT__

If you visited a website at an IP address, how does it know the name of the domain?

__SOLUTION__

```
$ wget https://2018shell.picoctf.com/static/311cab88f8331b8cd1285ae0d90a43f1/myname.pcap --no-check-certificate
```

Again we are given a `.pcap` file and we have to find the flag. Here the hint talks about domain so basically we are looking for [DNS servers](https://www.cloudflare.com/learning/dns/what-is-dns/).

Search for `dns`, you'll be left with two entries, double click on the second one:
```
55	1418.342859	192.168.2.12	192.168.2.1	DNS	316	Standard query response 0xaaa0 ANY thisismyname.com A 192.168.2.13 CNAME myname.com MX 5 myname.com MX 10 mx2.myname.com MX 20 mx3.myname.com NS ns1.myname.com NS ns2.myname.com TXT SOA ns1.thisismyname.com
```

Then click on `Domain Name System (response)` there in the `Answers` field you'll see the flag.

FLAG - `picoCTF{w4lt3r_wh1t3_33ddc9bcc77f22a319515c59736f64a2}`

