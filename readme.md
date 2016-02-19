
# Sagitta

This project is a python wrapper to interface with Sagitta webservices. It was written hastily but has proven it's worth over and over again. 

## Installation

Just download or clone this project then run
``` bash 

    python setup.py install

```

## Usage

The Sagitta class takes 7 parameters to initalize. In the example below logins.py looks something like this: 

``` python 

    # logins.py
    
    sagitta = dict(
        account='example',
        username='jsmith',
        password='SmithRocks!',
        accessCode='',
        serverPool='serverpool1',
        onlineCode='',
        wsServer='server02'
    )

```

``` python

import logins
from sagitta import Sagitta

# create the Sagitta object by passing in login creds. see logins.py
s = Sagitta(**logins.sagitta)

response = s.call('rolodexStartsWith', 'smith')
print(response)

"""
(startsWithInfoMap){
   TotalHits = 1
   TotalReturned = 1
   startsWithArray =
      (ArrayOfStartsWithArray){
         startsWithArray[] =
            (startsWithArray){
               ID = 234550
               ClientCd = "SMITHJOHN"
               ClientName = "JOHN SMITH"
               Addr1 = "221 B BAKER ST."
               City = "Memphis"
               StateProvCd = "TN"
               PostalCode = "37204"
               Producer1Cd = "PJW"
               Servicer1Cd = "ASD"
               Archived = None
               ContactMethod = "555 555-5555"
               Note = None
               SIC1Cd = None
               SourceCd = None
            },
      }
 }
"""

```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

Nothing to see here yet folks

## License

MIT: [http://rem.mit-license.org](http://rem.mit-license.org)
