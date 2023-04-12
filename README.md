# Simple Proxy

This is a simple HTTP/HTTPS proxy - designed to be distributed as a self-contained binary that can be dropped in
anywhere and run.

Code based on the guide here: <https://medium.com/@mlowicki/http-s-proxy-in-golang-in-less-than-100-lines-of-code-6a51c2f2c38c>

See also https://medium.com/@mlowicki/https-proxies-support-in-go-1-10-b956fb501d6b

and https://blog.cloudflare.com/the-complete-guide-to-golang-net-http-timeouts/

and this to setup upstream proxy: https://pkg.go.dev/net/http.

## Features

- HTTP and HTTPS.
- Can choose which port to run on.
- Can specify paths to certificate and private key file to use.
- Logs each proxied connection.
- Log options can be supplied using `glog`.
  - Can choose the log verbosity with the `-v` flag.
  - Can choose to log to a file.
- Basic authentication.
- Can log request headers.
- Can log failed authentication attempt details.
- Printing version number.

## Install

You can download the latest release for your architecture and operating system from [the releases
page](https://github.com/jthomperoo/simple-proxy/releases).

Once you unzip the release package you can either run the binary directly, or you can add it into your PATH so it can
be called from anywhere (e.g. the `/usr/bin` directory).

### Linux AMD64

You can use `wget` to download and install the program to your `/usr/bin` directory by running these commands:

```bash
wget https://github.com/jthomperoo/simple-proxy/releases/download/v1.1.0/simple-proxy_linux_amd64.zip
unzip -d simple-proxy simple-proxy_linux_amd64.zip
cp simple-proxy/simple-proxy /usr/bin/simple-proxy
rm -r simple-proxy/ simple-proxy_linux_amd64.zip
```

## Usage

You can download the binary and run the program directly (it is fully self contained).

## Linux/MacOS

You can run the binary directly:

```bash
./simple-proxy
```

## Windows

You can run the binary directly:

```bash
simple-proxy.exe
```

## Options

The program has the following options, you can see this list by using the `--help` flag.

```bash
Usage of simple-proxy:
  -alsologtostderr
    	log to standard error as well as files
  -basic-auth string
    	basic auth, format 'username:password', no auth if not provided
  -cert string
    	path to cert file
  -key string
    	path to key file
  -log-auth
    	log failed proxy auth details
  -log-headers
    	log request headers
  -log_backtrace_at value
    	when logging hits line file:N, emit a stack trace
  -log_dir string
    	If non-empty, write log files in this directory
  -logtostderr
    	log to standard error instead of files
  -port string
    	proxy port to listen on (default "8888")
  -protocol string
    	proxy protocol (http or https) (default "http")
  -stderrthreshold value
    	logs at or above this threshold go to stderr
  -timeout int
    	timeout in seconds (default 10)
  -v value
    	log level for V logs
  -version
    	prints current simple-proxy version
  -vmodule value
    	comma-separated list of pattern=N settings for file-filtered logging
```

## Contributing

See the [CONTRIBUTING](./CONTRIBUTING.md) and [CODE OF CONDUCT](./CODE_OF_CONDUCT.md) documents.
