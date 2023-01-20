
1. Request 

Authentifizieren

```
POST /api/v2/auth HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Content-Length: 119

{
	"api_key": "test_2dhjebat7wtsvtk4eaewmqco2_testmike",
	"api_secret": "hQejrud2RHMs4xgkH9BKEMurALC85TCrJiy7jTNoiH5"
}
```

Der Response wird ein Authentication und ein Refresh Token zurück liefern, die sicher gespeichert werden müssen:

```json
{
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw",
    "access_token_claims": {
        "env": "TEST",
        "organization_id": "281c4fca-6563-4548-b5ea-2af1065a78a2"
    },
    "access_token_expires_in": 80938,
    "access_token_expires_at": 1674318108,
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICI5NDQxMWU1MC00OTVkLTRlMTYtODcyOS04MWIwZjg1YmVmMjYifQ.eyJqdGkiOiIwMGM5NzgyNC1kYWFlLTQ2YTQtYWIxYy02MWIxYzI1M2JiNGIiLCJleHAiOjE2NzQ0MDQ1MDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsImF1ZCI6Imh0dHBzOi8vYXV0aC5maXNrYWx5LmNvbS9hdXRoL3JlYWxtcy9maXNrYWx5Iiwic3ViIjoiZDRiNjI5MWQtZjc5ZC00NDFhLWE0Y2QtNzgxZWMzZWU1N2IwIiwidHlwIjoiUmVmcmVzaCIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsInNjb3BlIjoib3JnYW5pemF0aW9uIn0._BWF9-PyBIWSYPnrOub_ojW8ean_cfZkOc67NkVjJ68",
    "refresh_token_expires_in": 167338,
    "refresh_token_expires_at": 1674404508
}
```

2. Request

TSE Erstellen

```
PUT /api/v2/tss/f80cd759-8403-48c6-a1a5-7922d1aa879e HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 66

{
    "metadata": {
        "custom_field": "custom_value"
    }
}
```

Response:

wichtig, die Admin PUK an dieser Stelle zu spiechern, sonst kann man die TSE nicht mehr löschen, sobald sie den status von "Created" zu einem anderen wechselt!

```json
{
    "certificate": "MIIB0jCCAVmgAwIBAgIhAMobwlPdEVOnr5JPBPcvcCAMiDrC7/pMNzczh122I7SuMAoGCCqGSM49BAMDMDExFTATBgNVBAoTDGZpc2thbHkgR21iSDEYMBYGA1UEAxMPZmlza2FseSBUZXN0IENBMB4XDTIzMDEwMzEwNTA1OFoXDTI0MDEwMzEwNTA1OFowMjEVMBMGA1UEChMMZmlza2FseSBHbWJIMRkwFwYDVQQDExBmaXNrYWx5IFRlc3QgVFNFMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAE9e1VAeNDrppfGElT3yUzQOn3YowdzBMnxTQTYpf+hSz5udiHMlu5XwBJue126zVPDpK4jL+q+eUTGabaKQyjaqNBMD8wDgYDVR0PAQH/BAQDAgeAMAwGA1UdEwEB/wQCMAAwHwYDVR0jBBgwFoAUlllBymQBup6ldKGojZVpZtWG5tQwCgYIKoZIzj0EAwMDZwAwZAIwS0LuaezTBy7JCgDnExujpwgLvQy/7zL9ak7HsjobiJllSrw579Rj8S1Of/o18FM+AjBzduQpQm7iBvrzyqx3wVZasaEhY7/kechwOPGOE2lQTM27TgfDlmbeWm9xATRjugM=",
    "serial_number": "ca1bc253dd1153a7af924f04f72f70200c883ac2effa4c373733875db623b4ae",
    "public_key": "BPXtVQHjQ66aXxhJU98lM0Dp92KMHcwTJ8U0E2KX/oUs+bnYhzJbuV8ASbntdus1Tw6SuIy/qvnlExmm2ikMo2o=",
    "signature_algorithm": "ecdsa-plain-SHA256",
    "signature_timestamp_format": "unixTime",
    "transaction_data_encoding": "UTF-8",
    "max_number_registered_clients": 199,
    "max_number_active_transactions": 2000,
    "supported_update_variants": "SIGNED",
    "metadata": {
        "custom_field": "custom_value"
    },
    "_id": "ed3e33f5-5a4c-4544-bedb-65aa27d078dd",
    "_type": "TSS",
    "_env": "TEST",
    "_version": "2.0.34",
    "time_creation": 1674237358,
    "admin_puk": "3208775922",
    "state": "CREATED"
}
```

3. Request:

TSE status ändern zu "UNINITIALIZED"

```
PATCH /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676 HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 32

{
    "state": "UNINITIALIZED"
}

```

Response:

```json
{
    "_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "state": "UNINITIALIZED",
    "time_creation": 1674237654,
    "time_uninit": 1674237725,
    "certificate": "MIIB0zCCAVmgAwIBAgIhAKQIRZKJ6lG29JLfeiQnLDlfoKSCAkU4neoV66ifbhL3MAoGCCqGSM49BAMDMDExFTATBgNVBAoTDGZpc2thbHkgR21iSDEYMBYGA1UEAxMPZmlza2FseSBUZXN0IENBMB4XDTIzMDEwMzEwNTA1OVoXDTI0MDEwMzEwNTA1OVowMjEVMBMGA1UEChMMZmlza2FseSBHbWJIMRkwFwYDVQQDExBmaXNrYWx5IFRlc3QgVFNFMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAE7xIYQTLLoplB5n6Btokr0D2zxSQ1nw2FS63e3YEH0P2F4KT+slHAQoglQINyMseXtzczqNnyur3zNh64u6Ksd6NBMD8wDgYDVR0PAQH/BAQDAgeAMAwGA1UdEwEB/wQCMAAwHwYDVR0jBBgwFoAUlllBymQBup6ldKGojZVpZtWG5tQwCgYIKoZIzj0EAwMDaAAwZQIwdqQOYp62PF70DZJPu8mmkb4Hn3v9M/7qk3AXML2vo8ckx+G5eWs3pRFUSaFqevz1AjEAzbhxI5OrNjgIhjLViTSA90XiCYW4y9PA7ey9OC+mI1+qyCXyXnumi4xRH2PIWPup",
    "serial_number": "a408459289ea51b6f492df7a24272c395fa0a4820245389dea15eba89f6e12f7",
    "public_key": "BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc=",
    "signature_counter": "24",
    "signature_algorithm": "ecdsa-plain-SHA256",
    "signature_timestamp_format": "unixTime",
    "transaction_data_encoding": "UTF-8",
    "number_registered_clients": 0,
    "max_number_registered_clients": 199,
    "number_active_transactions": 0,
    "max_number_active_transactions": 2000,
    "supported_update_variants": "SIGNED",
    "metadata": {
        "custom_field": "custom_value"
    },
    "_type": "TSS",
    "_env": "TEST",
    "_version": "2.0.34"
}
```

4. Request

Metadaten der TSE ändern

```
PATCH /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/metadata HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 85

{
    "custom_field": "modified_custom_value",
    "custom_field2": "custom_value2"
}
```

Response:

```json
{
    "custom_field": "modified_custom_value",
    "custom_field2": "custom_value2"
}
```

5. Request:

Um eine TSE zu initialisieren oder deaktivieren wird dieser Scritt gebraucht
Dafür wird die Admin PUK gebraucht um eine Admin PIN zu setzen mit der man später den Admin authentifizieren kann


```
PATCH /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/admin HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 68

{
    "admin_puk": "8920976146",
    "new_admin_pin": "1234567890"
}
```

Return

```json
200 OK EMPTY BODY
```

6. Request

Admin autentifizieren

```
POST /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/admin/auth HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 30

{
	"admin_pin": "1234567890"
}
```

Return:

```json
200 OK EMPTY BODY
```

7. Request

TSE initialisieren

```
PATCH /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676 HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 30

{
    "state": "INITIALIZED"
}
```

Response

```json
{
    "_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "description": "fiskaly sign cloud-TSE (cdb96888-86f5-4b5e-b213-ef265ecc4676)",
    "state": "INITIALIZED",
    "time_creation": 1674237654,
    "time_uninit": 1674237725,
    "time_init": 1674238342,
    "certificate": "MIIB0zCCAVmgAwIBAgIhAKQIRZKJ6lG29JLfeiQnLDlfoKSCAkU4neoV66ifbhL3MAoGCCqGSM49BAMDMDExFTATBgNVBAoTDGZpc2thbHkgR21iSDEYMBYGA1UEAxMPZmlza2FseSBUZXN0IENBMB4XDTIzMDEwMzEwNTA1OVoXDTI0MDEwMzEwNTA1OVowMjEVMBMGA1UEChMMZmlza2FseSBHbWJIMRkwFwYDVQQDExBmaXNrYWx5IFRlc3QgVFNFMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAE7xIYQTLLoplB5n6Btokr0D2zxSQ1nw2FS63e3YEH0P2F4KT+slHAQoglQINyMseXtzczqNnyur3zNh64u6Ksd6NBMD8wDgYDVR0PAQH/BAQDAgeAMAwGA1UdEwEB/wQCMAAwHwYDVR0jBBgwFoAUlllBymQBup6ldKGojZVpZtWG5tQwCgYIKoZIzj0EAwMDaAAwZQIwdqQOYp62PF70DZJPu8mmkb4Hn3v9M/7qk3AXML2vo8ckx+G5eWs3pRFUSaFqevz1AjEAzbhxI5OrNjgIhjLViTSA90XiCYW4y9PA7ey9OC+mI1+qyCXyXnumi4xRH2PIWPup",
    "serial_number": "a408459289ea51b6f492df7a24272c395fa0a4820245389dea15eba89f6e12f7",
    "public_key": "BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc=",
    "signature_counter": "27",
    "signature_algorithm": "ecdsa-plain-SHA256",
    "signature_timestamp_format": "unixTime",
    "transaction_data_encoding": "UTF-8",
    "number_registered_clients": 0,
    "max_number_registered_clients": 199,
    "number_active_transactions": 0,
    "max_number_active_transactions": 2000,
    "supported_update_variants": "SIGNED",
    "_type": "TSS",
    "_env": "TEST",
    "_version": "2.0.34"
}
```

8. Request:


Client erstellen

```
PUT /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/client/dbbf8759-bb15-421d-bc2e-777c6bce874c HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 128

{
	"serial_number": "ERS 76a56f21-c647-4b60-92e8-396acdf8fc56",
    "metadata": {
        "custom_field": "custom_value"
    }
}
```

Response:

```json
{
    "_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e",
    "state": "REGISTERED",
    "serial_number": "ERS f3ab7b96-6d82-433e-a87a-cccc8e001e20",
    "time_creation": 1674238550,
    "tss_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "metadata": {
        "custom_field": "custom_value"
    },
    "_type": "CLIENT",
    "_env": "TEST",
    "_version": "2.0.34"
}
```

9. Request:

Deregister client

```
PATCH /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/client/a32168e1-6bd2-4dca-b421-8e4176649c8e HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 28

{
	"state": "DEREGISTERED"
}
```

Response:

```json
{
    "_id": "a32168e1-6bd2-4dca-b421-8e4176649c8e",
    "state": "DEREGISTERED",
    "serial_number": "ERS b137e04a-375c-49a5-b90f-e83b33b5638a",
    "time_creation": 1674238644,
    "time_update": 1674238690,
    "tss_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "metadata": {
        "custom_field": "client 2"
    },
    "_type": "CLIENT",
    "_env": "TEST",
    "_version": "2.0.34"
}
```

10. Request:

Admin Ausloggen

```
POST /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/admin/logout HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 2

{}
```

Response:

```json
200 OK NO BODY
```

11. Request:

Transaktion starten

```
PUT /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/tx/c52435d2-0423-407c-9e03-8316499e3a4e?tx_revision=1 HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 76

{
	"state": "ACTIVE",
	"client_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e"
}
```

Response:

```json
{
    "schema": {},
    "state": "ACTIVE",
    "tss_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "tss_serial_number": "a408459289ea51b6f492df7a24272c395fa0a4820245389dea15eba89f6e12f7",
    "client_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e",
    "client_serial_number": "ERS f3ab7b96-6d82-433e-a87a-cccc8e001e20",
    "revision": 1,
    "latest_revision": 1,
    "number": 1,
    "time_start": 1674239242,
    "_id": "9e6f21ab-2eb5-42e3-98f0-3879881dd51d",
    "_type": "TRANSACTION",
    "_env": "TEST",
    "_version": "2.0.34",
    "signature": {
        "value": "FcQi1nbTeKr3cXqNkwDhYAJpjvcZau+MSKkrx8fp2DNXUqCh3xn9IPS0bc164J61gp4ZyQTvQ6YuHq3wECblxA==",
        "algorithm": "ecdsa-plain-SHA256",
        "counter": 32,
        "public_key": "BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc="
    },
    "log": {
        "operation": "Start",
        "timestamp": 1674239242,
        "timestamp_format": "unixTime"
    }
}
```

12. Request:

Transaktion Aktualisieren

```
PUT /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/tx/9e6f21ab-2eb5-42e3-98f0-3879881dd51d?tx_revision=2 HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 383

{
	"schema": {
		"standard_v1": {
			"receipt": {
				"receipt_type": "RECEIPT",
				"amounts_per_vat_rate": [
					{
						"vat_rate": "NORMAL",
						"amount": "21.42"
					}
				],
				"amounts_per_payment_type": [
					{
						"payment_type": "NON_CASH",
						"amount": "21.42"
					}
				]
			}
		}
	},
	"state": "ACTIVE",
	"client_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e"
}
```

Response:

```json
{
    "schema": {
        "standard_v1": {
            "receipt": {
                "amounts_per_payment_type": [
                    {
                        "amount": "21.42",
                        "currency_code": "EUR",
                        "payment_type": "NON_CASH"
                    }
                ],
                "amounts_per_vat_rate": [
                    {
                        "amount": "21.42",
                        "vat_rate": "NORMAL"
                    }
                ],
                "receipt_type": "RECEIPT"
            }
        },
        "raw": {
            "process_type": "Kassenbeleg-V1",
            "process_data": "QmVsZWdeMjEuNDJfMC4wMF8wLjAwXzAuMDBfMC4wMF4yMS40MjpVbmJhcg=="
        }
    },
    "state": "ACTIVE",
    "tss_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "tss_serial_number": "a408459289ea51b6f492df7a24272c395fa0a4820245389dea15eba89f6e12f7",
    "client_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e",
    "client_serial_number": "ERS f3ab7b96-6d82-433e-a87a-cccc8e001e20",
    "revision": 2,
    "latest_revision": 2,
    "number": 1,
    "time_start": 1674239242,
    "_id": "9e6f21ab-2eb5-42e3-98f0-3879881dd51d",
    "_type": "TRANSACTION",
    "_env": "TEST",
    "_version": "2.0.34",
    "signature": {
        "value": "KAmWSD0eqeOBRdjWk6JWNUHH6pVxGQxjs6Uwvw/Sh/w7qO5B+IAghZEjwwt4jIGeyVm6DCb4Zynr8bZQTsQxtw==",
        "algorithm": "ecdsa-plain-SHA256",
        "counter": 33,
        "public_key": "BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc="
    },
    "log": {
        "operation": "Update",
        "timestamp": 1674239505,
        "timestamp_format": "unixTime"
    }
}
```

13. Request:

Transaktion beenden

```
PUT /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676/tx/9e6f21ab-2eb5-42e3-98f0-3879881dd51d?tx_revision=3 HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 385

{
	"schema": {
		"standard_v1": {
			"receipt": {
				"receipt_type": "RECEIPT",
				"amounts_per_vat_rate": [
					{
						"vat_rate": "NORMAL",
						"amount": "21.42"
					}
				],
				"amounts_per_payment_type": [
					{
						"payment_type": "NON_CASH",
						"amount": "21.42"
					}
				]
			}
		}
	},
	"state": "FINISHED",
	"client_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e"
}
```


Response:

```json
{
    "schema": {
        "standard_v1": {
            "receipt": {
                "amounts_per_payment_type": [
                    {
                        "amount": "21.42",
                        "currency_code": "EUR",
                        "payment_type": "NON_CASH"
                    }
                ],
                "amounts_per_vat_rate": [
                    {
                        "amount": "21.42",
                        "vat_rate": "NORMAL"
                    }
                ],
                "receipt_type": "RECEIPT"
            }
        },
        "raw": {
            "process_type": "Kassenbeleg-V1",
            "process_data": "QmVsZWdeMjEuNDJfMC4wMF8wLjAwXzAuMDBfMC4wMF4yMS40MjpVbmJhcg=="
        }
    },
    "state": "FINISHED",
    "tss_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "tss_serial_number": "a408459289ea51b6f492df7a24272c395fa0a4820245389dea15eba89f6e12f7",
    "client_id": "d884dfc1-b8d6-4c59-a41f-2c33c916f30e",
    "client_serial_number": "ERS f3ab7b96-6d82-433e-a87a-cccc8e001e20",
    "revision": 3,
    "latest_revision": 3,
    "number": 1,
    "time_start": 1674239242,
    "time_end": 1674239587,
    "_id": "9e6f21ab-2eb5-42e3-98f0-3879881dd51d",
    "_type": "TRANSACTION",
    "_env": "TEST",
    "_version": "2.0.34",
    "signature": {
        "value": "qvyQJduZN29b2kXpEqhXlJ0Hmy3rYiPzBiu/QTPPei7bnGIwMysPV3Q39gMwoEfxtp3KXqWEfUrBulTcBbRpRQ==",
        "algorithm": "ecdsa-plain-SHA256",
        "counter": 34,
        "public_key": "BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc="
    },
    "log": {
        "operation": "Finish",
        "timestamp": 1674239587,
        "timestamp_format": "unixTime"
    },
    "qr_code_data": "V0;ERS f3ab7b96-6d82-433e-a87a-cccc8e001e20;Kassenbeleg-V1;Beleg^21.42_0.00_0.00_0.00_0.00^21.42:Unbar;1;34;2023-01-20T18:27:22.000Z;2023-01-20T18:33:07.000Z;ecdsa-plain-SHA256;unixTime;qvyQJduZN29b2kXpEqhXlJ0Hmy3rYiPzBiu/QTPPei7bnGIwMysPV3Q39gMwoEfxtp3KXqWEfUrBulTcBbRpRQ==;BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc="
}
```

14. Request

Disable TSE, dafür muss der Admin authentifiziert sein

```
PATCH /api/v2/tss/cdb96888-86f5-4b5e-b213-ef265ecc4676 HTTP/1.1
Host: kassensichv-middleware.fiskaly.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJTTm5CU0hCTUljQUpBalczaUhDNFRWOTR4MFZCeU00S25LSFJ0eU8tdnBnIn0.eyJqdGkiOiIyMmQxMTAxYy03ZDg4LTQwODEtOTBiMS00MmRmYzQ3YzNmNGYiLCJleHAiOjE2NzQzMTgxMDgsIm5iZiI6MCwiaWF0IjoxNjc0MjMxNzA4LCJpc3MiOiJodHRwczovL2F1dGguZmlza2FseS5jb20vYXV0aC9yZWFsbXMvZmlza2FseSIsInN1YiI6ImQ0YjYyOTFkLWY3OWQtNDQxYS1hNGNkLTc4MWVjM2VlNTdiMCIsInR5cCI6IkJlYXJlciIsImF6cCI6Imthc3NlbnNpY2h2LWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6ImE4ODE2NTMwLThjY2QtNDg2Ni05ZTdiLTM5MjQxM2MyMmU1MCIsImFjciI6IjEiLCJzY29wZSI6Im9yZ2FuaXphdGlvbiIsIm9yZ2FuaXphdGlvbiI6IjI4MWM0ZmNhLTY1NjMtNDU0OC1iNWVhLTJhZjEwNjVhNzhhMiIsInR5cGUiOiJBUElfS0VZIiwiZW52IjoiVEVTVCJ9.GE6ADHAik5BGoRmndBuWsxDRKJdEP8ScExT5WWtKZtqZAV-crJ5nLYhjMDfws_MV3ZrHWXTEYLoMg7vySv9CGAPG02hQOrzdEduE30kF06WK7D43jVNGgVuWQq_vHJKIetIst82yZV59S_d1bG8033whwbXeQj738_fNHSALEh-x1mgyrUVp9P5Kp-bqvJg3WWRpSeVLpGUv4RrtRhd8UaVS6ewFDqAmSBxh8-tHdJ-r4h4cmuyPhubMneQ6_Pt7bhYUtjHM89uDzlemK8ZWXDoFBpPksZypBzCyNxjaX2wGd5xFJdx6aKgTB8Ws_sSXtewVi3mFpypsdxSgXQpqlw
Content-Length: 27

{
    "state": "DISABLED"
}
```


Response:

```json
{
    "_id": "cdb96888-86f5-4b5e-b213-ef265ecc4676",
    "description": "fiskaly sign cloud-TSE (cdb96888-86f5-4b5e-b213-ef265ecc4676)",
    "state": "DISABLED",
    "time_creation": 1674237654,
    "time_uninit": 1674237725,
    "time_init": 1674238342,
    "time_disable": 1674239801,
    "certificate": "MIIB0zCCAVmgAwIBAgIhAKQIRZKJ6lG29JLfeiQnLDlfoKSCAkU4neoV66ifbhL3MAoGCCqGSM49BAMDMDExFTATBgNVBAoTDGZpc2thbHkgR21iSDEYMBYGA1UEAxMPZmlza2FseSBUZXN0IENBMB4XDTIzMDEwMzEwNTA1OVoXDTI0MDEwMzEwNTA1OVowMjEVMBMGA1UEChMMZmlza2FseSBHbWJIMRkwFwYDVQQDExBmaXNrYWx5IFRlc3QgVFNFMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAE7xIYQTLLoplB5n6Btokr0D2zxSQ1nw2FS63e3YEH0P2F4KT+slHAQoglQINyMseXtzczqNnyur3zNh64u6Ksd6NBMD8wDgYDVR0PAQH/BAQDAgeAMAwGA1UdEwEB/wQCMAAwHwYDVR0jBBgwFoAUlllBymQBup6ldKGojZVpZtWG5tQwCgYIKoZIzj0EAwMDaAAwZQIwdqQOYp62PF70DZJPu8mmkb4Hn3v9M/7qk3AXML2vo8ckx+G5eWs3pRFUSaFqevz1AjEAzbhxI5OrNjgIhjLViTSA90XiCYW4y9PA7ey9OC+mI1+qyCXyXnumi4xRH2PIWPup",
    "serial_number": "a408459289ea51b6f492df7a24272c395fa0a4820245389dea15eba89f6e12f7",
    "public_key": "BO8SGEEyy6KZQeZ+gbaJK9A9s8UkNZ8NhUut3t2BB9D9heCk/rJRwEKIJUCDcjLHl7c3M6jZ8rq98zYeuLuirHc=",
    "signature_counter": "36",
    "signature_algorithm": "ecdsa-plain-SHA256",
    "signature_timestamp_format": "unixTime",
    "transaction_counter": "1",
    "transaction_data_encoding": "UTF-8",
    "number_registered_clients": 1,
    "max_number_registered_clients": 199,
    "number_active_transactions": 0,
    "max_number_active_transactions": 2000,
    "supported_update_variants": "SIGNED",
    "_type": "TSS",
    "_env": "TEST",
    "_version": "2.0.34"
}
```
