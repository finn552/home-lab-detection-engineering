# DataCamp Sensitive File Exposure (Recon)

**Date Discovered:** July 8, 2025  
**Reported to Program:** Yes  
**Status:** Under triage  
**Severity:** Medium → High (depending on internal access level)  
**Tool Used:** FFUF (v1.5.0-dev)  

---

## Summary

During directory brute-forcing on a subdomain of [DataCamp](https://poser.datacamp.com), several sensitive file paths responded with HTTP `403 Forbidden` rather than the expected `404 Not Found`. This indicates the files **exist on the server** and access is being denied, suggesting **improper access control** and **potential sensitive config leakage**.

---

## Target
https://poser.datacamp.com

---

## Tools and Wordlist

- Tool: `ffuf`
- Wordlist: `SecLists/Discovery/Web-Content/common.txt`

---

## Command Used

```bash
ffuf -w ~/SecLists/Discovery/Web-Content/common.txt \
-u https://poser.datacamp.com/FUZZ \
-mc 200,403,500 -fc 404 -t 50 -o poser_pages.txt
```
## Screenshots of bug report to Datacomp through intigriti
<img width="907" alt="Screenshot 2025-07-09 at 22 41 20" src="https://github.com/user-attachments/assets/f5be4ef1-1217-4891-9501-937fd16f3c06" />
<img width="891" alt="Screenshot 2025-07-09 at 22 41 56" src="https://github.com/user-attachments/assets/3d4ba571-79f3-4c30-86c2-4cf163cdb97b" />
<img width="900" alt="Screenshot 2025-07-09 at 22 42 12" src="https://github.com/user-attachments/assets/b5de7834-cbf4-42cf-a583-1c8a8d139744" />
<img width="883" alt="Screenshot 2025-07-09 at 22 42 28" src="https://github.com/user-attachments/assets/0c1651fb-0dc2-439a-8df2-d30213c2f62a" />


## Screenshots of commands run 
<img width="1467" alt="FFUF Terminal Scan Output" src="https://github.com/user-attachments/assets/9e7cc7e9-5742-450b-a955-6d7d2f91aaef" />
<img width="1470" alt="cat sizecheck json with jq Output 1" src="https://github.com/user-attachments/assets/d6b99e41-c0e7-49b0-83d0-08f0093a920d" />
<img width="1470" alt="cat sizecheck json with jq Output 2" src="https://github.com/user-attachments/assets/b702d139-782c-4114-8f08-4bb1dc389dab" />
<img width="1463" alt="curl x-original 1" src="https://github.com/user-attachments/assets/0cdda9b4-21b4-44ed-ac2f-11cb3e7f3980" />
<img width="1468" alt="curl x-original 2" src="https://github.com/user-attachments/assets/44c133d9-c14a-44af-aac9-488865eed974" />
<img width="1470" alt="curl x-original 3" src="https://github.com/user-attachments/assets/3e5b9922-7057-4b79-a30d-1960729768c2" />
<img width="1470" alt="curl x-original 4" src="https://github.com/user-attachments/assets/0078ca88-5baa-49ac-88f8-d70d0606182e" />
<img width="1470" alt="curl x-original 5" src="https://github.com/user-attachments/assets/39f08648-598c-4112-8685-d34de2495916" />
<img width="638" alt="Screenshot 2025-07-09 at 22 39 18" src="https://github.com/user-attachments/assets/ec220ea2-ff49-4ad2-9523-587140db9aab" />













