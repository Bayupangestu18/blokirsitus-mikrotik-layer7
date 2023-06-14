## Payload blokir situs dan file pada mikrotik layer 7 protocol

blokir situs masukkan kode ini di layer 7 protocol
`^.+(urlsitus).*$`

blokir file masukkan kode ini di layer 7 protocol
`GET .*(\.pdf)[^a-zA-Z0-9].*HTTP.*\n`
