A simple tcp port scanner and banner grabber.  Logs output as json.

You probably want to be using [massscan](https://github.com/robertdavidgraham/masscan).

Usage:

          --banner-timeout duration   timeout when fetching banner (default 2s)
          --debug                     sets log level to debug
      -x, --exclude stringSlice       cidr blocks to exclude
          --parallel                  Scan multiple ports on each host in parallel
      -p, --port stringSlice          ports to scan. ex: 80,443,8000-8100
          --pretty                    use pretty logs
          --rate int                  rate in attempts/sec (default 1000)
          --timeout duration          Scan connection timeout (default 2s)

Example:

   # time PORTS=5038 RATE=2000 IP=195.90.1.0/24  ./bannerscanner 
{"level":"info","state":"open","host":"195.90.1.128","port":5038,"banner":"\r\n\r\n","time":"2020-10-06T16:12:17Z","message":"found service"}
{"level":"info","state":"open","host":"195.90.1.143","port":5038,"banner":"\ufffd\ufffd,","time":"2020-10-06T16:12:17Z","message":"found service"}

real	0m2.025s
user	0m0.010s
sys	0m0.022s
[root]#
