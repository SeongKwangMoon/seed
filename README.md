# Orig Repo
https://github.com/geeksbaek/seed

---
## FIXED
- pdwRoundKey was not setted (Round key setting error)
- Function in the process of create round key, `encRoundKeyUpdate1` was misimplemented.

---

Matched KISA's test vector
https://seed.kisa.or.kr/kisa/algorithm/EgovSeedInfo.do - `참조구현값` file, `[5]_SEED+128_Test_Vector_M.pdf`
```
Key: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
Plaintext: 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

round1  input: &[7C8F8C7E C737A22C] &[00010203] &[04050607] &[08090A0B] &[0C0D0E0F]
round2  input: &[FF276CDB A7CA684A] &[08090A0B] &[0C0D0E0F] &[8081BC57] &[C4EA8A1F]
round3  input: &[2F9D01A1 70049E41] &[8081BC57] &[C4EA8A1F] &[117A8B07] &[D7358C24]
round4  input: &[AE59B3C4 4245E90C] &[117A8B07] &[D7358C24] &[D1738C94] &[7326CAB0]
round5  input: &[A1D6400F DBC1394E] &[D1738C94] &[7326CAB0] &[577ECE6D] &[1F8433EC]
round6  input: &[85963508 0C5F1FCB] &[577ECE6D] &[1F8433EC] &[910F62AB] &[DDA096C1]
round7  input: &[B684BDA7 61A4AEAE] &[910F62AB] &[DDA096C1] &[EA4D39B4] &[B17B1938]
round8  input: &[D17E0741 FEE90AA1] &[EA4D39B4] &[B17B1938] &[B04E251F] &[97D7442C]
round9  input: &[76CC05D5 E97A7394] &[B04E251F] &[97D7442C] &[B86D31BF] &[A5988C06]
round10 input: &[50AC6F92 1B2666E5] &[B86D31BF] &[A5988C06] &[9008EABF] &[38DF7430]
round11 input: &[65B7904A 8EC3A7B3] &[9008EABF] &[38DF7430] &[33E47DE0] &[54EFF76C]
round12 input: &[2F7E2E22 A2B121B9] &[33E47DE0] &[54EFF76C] &[6BE9C434] &[BF3F378A]
round13 input: &[4D0BFDE4 4E888D9B] &[6BE9C434] &[BF3F378A] &[B8DC3842] &[03A02D33]
round14 input: &[631C8DDC 4378A6C4] &[B8DC3842] &[03A02D33] &[6679FCF7] &[9791DFCB]
round15 input: &[216AF65F 7878C031] &[6679FCF7] &[9791DFCB] &[1A415792] &[A02B8C54]
round16 input: &[71891150 98B255B0] &[1A415792] &[A02B8C54] &[19AFF1CC] &[6D346CDB]
Ciphertext: 5E BA C6 E0 05 4E 16 68 19 AF F1 CC 6D 34 6C DB
...
DECRYPTED plaintext: 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
```