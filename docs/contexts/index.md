#### [View on GitHub](https://github.com/w3c-ccg/lds-jws2020)

> JSON-LD 1.1 is being formally specified in the W3C JSON-LD Working Group. To participate in this work, please join the W3C and then [join the Working Group](https://www.w3.org/2018/json-ld-wg/).

- [Latest JSON-LD Context](https://w3c-ccg.github.io/lds-jws2020/contexts/lds-jws2020-v0.0.jsonld)

### Suite Details

Per [ld-signatures](https://w3c-dvcg.github.io/ld-signatures/#signature-suites), this Signature Suite defines the following:

```json
{
  "id": "https://w3c-ccg.github.io/lds-jws2020/contexts/#JsonWebSignature2020",
  "type": "SignatureSuite",
  "canonicalizationAlgorithm": "https://w3id.org/security#URDNA2015",
  "digestAlgorithm": "https://tools.ietf.org/html/rfc4634#section-4.2.2",
  "signatureAlgorithm": "https://www.iana.org/assignments/jose/jose.xhtml#web-signature-encryption-algorithms"
}
```

### Terminology

<h4 id="publicKeyJwk"><a href="#publicKeyJwk">publicKeyJwk</a></h4>

A public key in JWK format. A JSON Web Key (JWK) is a JavaScript Object Notation (JSON) data structure that represents a cryptographic key. Read [RFC7517](https://tools.ietf.org/html/rfc7517).

#### Example:

```json
{
  "@context": "https://w3c-ccg.github.io/lds-jws2020/contexts/lds-jws2020-v0.0.jsonld",
  "id": "did:example:123#JUvpllMEYUZ2joO59UNui_XYDqxVqiFLLAJ8klWuPBw",
  "type": "JwsVerificationKey2020",
  "publicKeyJwk": {
    "kid": "JUvpllMEYUZ2joO59UNui_XYDqxVqiFLLAJ8klWuPBw",
    "kty": "OKP",
    "crv": "Ed25519",
    "d": "nWGxne_9WmC6hEr0kuwsxERJxWl7MmkZcDusAxyuf2A",
    "x": "11qYAYKxCrfVS_7TyWQHOg7hcvPapiMlrwIaaPcHURo"
  }
}
```

<h4 id="JwsVerificationKey2020"><a href="#JwsVerificationKey2020">JwsVerificationKey2020</a></h4>

The verification key type for `JsonWebSignature2020`. The key must have a property `publicKeyJwk` and its value must be a valid JWK.

#### Example:

```json
[
  {
    "@context": "https://w3c-ccg.github.io/lds-jws2020/contexts/lds-jws2020-v0.0.jsonld",
    "id": "did:example:123#JUvpllMEYUZ2joO59UNui_XYDqxVqiFLLAJ8klWuPBw",
    "type": "JwsVerificationKey2020",
    "publicKeyJwk": {
      "kid": "JUvpllMEYUZ2joO59UNui_XYDqxVqiFLLAJ8klWuPBw",
      "kty": "OKP",
      "crv": "Ed25519",
      "d": "nWGxne_9WmC6hEr0kuwsxERJxWl7MmkZcDusAxyuf2A",
      "x": "11qYAYKxCrfVS_7TyWQHOg7hcvPapiMlrwIaaPcHURo"
    }
  }
]
```

<h4 id="JsonWebSignature2020"><a href="#JsonWebSignature2020">JsonWebSignature2020</a></h4>

A JSON-LD Document has been signed with JsonWebSignature2020,
when it contains a proof field with type `JsonWebSignature2020`. The proof must contain a key `jws` with value defined by the signing algorithm described here.

#### Example:

```json
{
  "@context": "https://w3id.org/security/v2",
  "http://schema.org/action": "AuthenticateMe",
  "proof": {
    "challenge": "abc",
    "created": "2019-01-16T20:13:10Z",
    "domain": "example.com",
    "proofPurpose": "authentication",
    "verificationMethod": "https://example.com/i/alice/keys/2",
    "type": "JsonWebSignature2020",
    "jws": "eyJhbGciOiJFUzI1NksiLCJiNjQiOmZhbHNlLCJjcml0IjpbImI2NCJdfQ..QgbRWT8w1LJet_KFofNfz_TVs27z4pwdPwUHhXYUaFlKicBQp6U1H5Kx-mST6uFvIyOqrYTJifDijZbtAfi0MA"
  }
}
```
