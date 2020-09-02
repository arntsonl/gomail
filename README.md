你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# Gomail
[![Build Status](https://travis-ci.org/gophish/gomail.svg)](https://travis-ci.org/gophish/gomail) [![Documentation](https://godoc.org/github.com/gophish/gomail?status.svg)](https://godoc.org/github.com/gophish/gomail)

## Introduction

Gomail is a simple and efficient package to send emails. It is well tested and
documented.

Gomail can only send emails using an SMTP server. But the API is flexible and it
is easy to implement other methods for sending emails using a local Postfix, an
API, etc.

It is versioned using [gopkg.in](https://gopkg.in) so I promise
there will never be backward incompatible changes within each version.

It requires Go 1.2 or newer. With Go 1.5, no external dependencies are used.


## Features

Gomail supports:
- Attachments
- Embedded images
- HTML and text templates
- Automatic encoding of special characters
- SSL and TLS
- Sending multiple emails with the same SMTP connection


## Documentation

https://godoc.org/github.com/gophish/gomail


## Download

    go get github.com/gophish/gomail


## Examples

See the [examples in the documentation](https://godoc.org/github.com/gophish/gomail#example-package).


## FAQ

### x509: certificate signed by unknown authority

If you get this error it means the certificate used by the SMTP server is not
considered valid by the client running Gomail. As a quick workaround you can
bypass the verification of the server's certificate chain and host name by using
`SetTLSConfig`:

    package main

    import (
    	"crypto/tls"

    	"github.com/gophish/gomail"
    )

    func main() {
    	d := gomail.NewDialer("smtp.example.com", 587, "user", "123456")
    	d.TLSConfig = &tls.Config{InsecureSkipVerify: true}

        // Send emails using d.
    }

Note, however, that this is insecure and should not be used in production.


## Contribute

Contributions are more than welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for
more info.


## Change log

See [CHANGELOG.md](CHANGELOG.md).


## License

[MIT](LICENSE)
