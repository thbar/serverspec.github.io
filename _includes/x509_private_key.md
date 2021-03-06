### <a name="x509_private_key">x509\_private\_key</a>

x509\_private\_key resource type

#### be_encrypted

Checks if given file contains an encryption signature:

```ruby
describe x509_private_key('/my/private/server-key.pem') do
  it { should_not be_encrypted }
end
```

#### be_valid

In order to check key integrity.

```ruby
describe x509_private_key('/my/private/server-key.pem') do
  it { should be_valid }
end
```

#### have\_matching\_certificate

In order to ensure that the private key modulus is equal to modulus of given certificate, that is, certificate has been created from key. 

```ruby
describe x509_private_key('/my/private/server-key.pem') do
  it { should have_matching_certificate('/my/certs/server-cert.pem') }
end
```
