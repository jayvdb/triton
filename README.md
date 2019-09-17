# Triton DNS client
Triton is a simple DNS client made for better understanding of DNS protocol

# Installation
## From PYPI

`pip3 install triton-dns-client`

## From this repo

`git clone https://git.best-service.online/yurzs/triton`  
`cd triron`  
`python3 setup.py` 

## How to use

Here is an example query for A record of this gitlab instance
```
import asyncio
import triton
reply_message = asyncio.run(triton.query('8.8.8.8', 'git.best-service.online', 1))
print(reply_message.__dict__)
>>> {'header':
 {'id': 10023,
  'qr': 1,
  'opcode': 0,
  'aa': 0,
  'tc': 0,
  'rd': 1,
  'ra': 1,
  'z': 0,
  'rcode':0,
  'qdcount': 1,
  'ancount': 1,
  'nscount': 0,
  'arcount': 0},
'question':
 [
   {'qname':"git.best-service.online",
    'qtype': 1, 'qclass': 1}
 ],
'answer': 
 [
   {'name': 'git.best-service.online',
    'type': 1,
    'class': 1,
    'ttl': 999,
    'rdata': {
      'address': 1356055586} # This is int repr of IP address
    }
 ],
'authority': [],
'additional': []}
``` 

## TODO List
- [ ] Enable EDNS
- [ ] Add DNSSEC Resource Record types


