### Configure your project nicely
    StartupAction 
        name: 'Logo' 
        code: [ PolymorphSystemSettings showDesktopLogo: false] .
    StartupAction 
        name: 'Git Settings' 
        code: [ 
            Iceberg enableMetacelloIntegration: true.
            IceCredentialStore current
                    storeCredential: (IcePlaintextCredentials new
                    username: 'xxxxxJohnDoe';
                    password: 'xxxPassOfJohnDoe';
                    host: 'github.com';
                    yourself).
            IceCredentialsProvider sshCredentials
                username: 'git';
                publicKey: 'Path to your public rsa file (public key)';
                privateKey: 'Path to your private rsa file (private key)'.
            IceCredentialStore current
                storeCredential: (IceTokenCredentials new
                    username: 'xxxxxJohnDoe';
                    token: 'magictoken here ';
                    yourself) 
                forHostname: 'github.com'.
            ]. 
}
  ...
  package: 'BaselineOfMyCoolProjectWithPharo'
  <baseline>
  spec
    for: #common
    do: [ spec package: 'MyCoolProjectWithPharo' ]
  baseline: 'MyCoolProjectWithPharo';
  repository: 'github://Ducasse/MyCoolProjectWithPharo/src';
  load