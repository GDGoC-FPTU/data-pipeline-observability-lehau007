[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573980&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.haulv@vinuni.edu.vn
**Student ID:** 2A202600110
**Name:** Lê Văn Hậu

---

## Mo ta

Bai lab xay dung mot ETL pipeline don gian de xu ly du lieu san pham truoc khi dua vao agent tra loi.
Pipeline gom 4 buoc: Extract du lieu JSON, Validate du lieu khong hop le, Transform theo business rule,
va Load thanh file CSV. Ngoai ra bai lab co phan stress test de so sanh chat luong cau tra loi cua agent
khi dung clean data va garbage data.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

Ket qua sau khi chay: tao file `processed_data.csv`.

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

Lenh tren se:
1) Tao `garbage_data.csv` chua cac loi data quality.
2) Chay mo phong agent voi 2 nguon tri thuc: clean data va garbage data.

### Chay local autograder test
```bash
pytest tests/test_autograder.py -q
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Raw records loaded: 5
- Valid records kept: 3
- Invalid records dropped: 2
- Output file: `processed_data.csv`
- Agent on clean data: chon Laptop ($1200), ket qua hop ly.
- Agent on garbage data: chon Nuclear Reactor ($999999), ket qua sai do outlier.
