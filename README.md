# renoscoin-docker
1.Build:

  A. locally:
  
    $ git clone https://github.com/onitsoft/renoscoin-docker.git
    $ docker build -t renoscoin-docker renoscoin-docker/
   
    
  B. Get from docker hub:
  
    $ docker pull onitsoft/renoscoin-docker:latest
    

2. create shared volume
```
$ mkdir renoscoin_data
```
3. coppy the renoscoing config file into the share volume
``` 
$ cp renoscoin-docker/renoscoin.conf renoscoin_data/
```

wget from GitHub raw version if you used docker hub if you used docker-hub (`docker pull`)

```
$ cd renoscoin_data && wget https://raw.githubusercontent.com/onitsoft/renoscoin-docker/master/renoscoin.conf
```

4. Run
```
$ docker run -d -p -p 65223:65223 -v {$PWD}/renoscoin_data:/root/renoscoin/data renoscoin-docker /bin/bash -c "/root/renoscoin/app/start.sh"
```

## License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
