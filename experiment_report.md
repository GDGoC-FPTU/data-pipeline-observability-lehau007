# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600110
**Name:** Lê Văn Hậu
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu sach giup agent tim dung electronics va tra loi hop ly. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Outlier gia qua lon lam ket qua bi sai lech nghiem trong. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trong bai nay chon san pham dua tren logic gia cao nhat trong category electronics.
Khi du lieu bi ban, rule don gian nay de bi danh lua boi outlier nhu Nuclear Reactor gia 999999,
nen agent ket luan sai du khong phu hop nhu cau thuc te. Ngoai ra, duplicate IDs lam giam do tin cay
cua thong tin, wrong data types nhu "ten dollars" co the gay loi parse hoac lam ham tinh toan bo qua
mot phan du lieu, va null values lam bo loc category bi nhiu. Tat ca cac loi chat luong du lieu deu
lam context retrieval kem chinh xac, dan den output nghe co ve "tu tin" nhung thuc chat sai. Vi vay,
neu khong co validation va cleaning truoc khi dua vao tac vu hoi dap, agent rat de hallucinate hoac
dua khuyen nghi nguy hiem.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt tot khong the cuu duoc du lieu xau. Neu du lieu dau vao sai, thieu, hoac bi outlier,
agent van tao ra cau tra loi sai mot cach rat thuyet phuc. Data quality la dieu kien nen tang,
con prompt quality la bo nhan manh hieu qua khi du lieu da dang tin cay.
