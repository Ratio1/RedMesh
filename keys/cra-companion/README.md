# RedMesh CRA Companion: keys

- `naeural-licence-2026-10.public.json`: the public half of NAEURAL SRL's licence signing key `naeural-licence-2026-10` (Ed25519). It verifies the licence in a partner key file and the list below. The application has the same key built in.
- `withdrawn-keys.json`: NAEURAL SRL's signed list of withdrawn partner keys. Each entry gives a key's ID, its partner's ID (opaque IDs, never a name) and the date the key was withdrawn. An empty list means that no key has been withdrawn.

From 1.0.2, when a connection is available and a partner key with a licence is installed, the application fetches the list at start and in `redmeshcra --check`. The request carries no partner, key or customer information. The application checks the list's signature and shows in Settings, Checks whether the installed key is on it. A list that cannot be fetched, or whose signature does not verify, is shown as "Not checked", never as withdrawn. No result stops work.

To check the list yourself, with Python 3 and the `cryptography` package, save these lines as `verify.py`:

```python
import base64, json, sys
from cryptography.hazmat.primitives.asymmetric.ed25519 import Ed25519PublicKey
key = json.load(open(sys.argv[1], encoding='utf-8'))
doc = json.load(open(sys.argv[2], encoding='utf-8'))
signature = base64.b64decode(doc.pop('signature'))
data = b'redmesh-cra-companion-withdrawn-v1\n' + (json.dumps(doc, sort_keys=True, indent=2, ensure_ascii=False) + '\n').encode('utf-8')
Ed25519PublicKey.from_public_bytes(base64.b64decode(key['public_key'])).verify(signature, data)
print('signature OK; issued', doc['issued_utc'], '; withdrawn keys:', len(doc['withdrawn']))
```

and run `python3 verify.py naeural-licence-2026-10.public.json withdrawn-keys.json`. It prints "signature OK" for the list as published, and stops with `InvalidSignature` if the list was changed.

Contact: redmesh@ratio1.ai
