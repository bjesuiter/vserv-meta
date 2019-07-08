# vserv-meta

A mateodelnorte/meta Project for managing all tools running on bjesuiter-vserv

## Included Projects

- [vserv-setup-manual](https://bitbucket.org/bnware/vserv-setup-manual)
- [vserv-reverse-proxy](https://bitbucket.org/bnware/vserv-reverse-proxy)
- [vserv-url-shortener-shlink](https://bitbucket.org/bnware/vserv-url-shortener-shlink)
- [polr-url-shortener-service](https://github.com/bjesuiter/polr-url-shortener-service)
- [vserv-nextcloud](https://bitbucket.org/bnware/vserv-nextcloud)
- [vserv-rancher](https://bitbucket.org/bnware/vserv-rancher/src/master/)

Important: All of these packages repos, hosted on bitbucket, 
where imported using `git@private.bitbucket.org`. 
The `private.bitbucket.org` host is defined in `~.ssh/config` 
with the correct ssh private key on jb-mbp-15.

**SSH Config**

    Host *private.bitbucket.org*
        HostName bitbucket.org
        User git
        # use correct IdentityFile per machine!
    	IdentityFile ~/.ssh/deployment@vserv
    
    # add private.bitbucket before bitbucket rule!
    Host *bitbucket.org*
    	IdentityFile ~/.ssh/deployment@vser

## TODO 

- enable Traefik API Dashboard in secure way: https://docs.traefik.io/configuration/api/
- Add multiple domains to one backend by adding them with comma to the `Host` rule:  

         [frontends.frontend2]
            [frontends.frontend2.routes.test_1]
            rule = "Host:test1.localhost,test2.localhost"
          [frontends.frontend3]
          backend = "backend2"
            [frontends.frontend3.routes.test_1]
            rule = "Path:/test1,/test2"
