## Job to remote command execution by SSH

***

#### 1
> Install "ssh" plugin - manage jenkins -> plugins -> available plugins

***

#### 2
> Add user (created in docker container) ssh username & credentials (private key) - manage jenkins -> credentials -> system -> global credentials -> add credentials

***

#### 3
> Add remote host configuration - manage jenkins -> system -> SSH remote hosts -> SSH sites (username as credentials with SSH port)

***

#### 4
> Create job (freestyle project) - as "execute shell script on remote host using ssh" (build steps section)
