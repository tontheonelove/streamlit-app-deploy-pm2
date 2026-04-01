# streamlit-app-deploy-pm2 💻


## โครงสร้างไฟล์ (ตัวอย่าง)

```
ic-billing-automate/
 ├── app.py
 ├── .env
 ├── requirements.txt
 └── ecosystem.config.js
```

## 1. Install lib with venv

```
(For Linux)
cd  your-app-path
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```


```
(For Windows)
cd  your-app-path
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```


## 2. edit ecosystem.config.js

```
module.exports = {
  apps: [{
    name: "your-app-name",
    script: "/root/your-app-name/venv/bin/python3",
    args: "-m streamlit run /root/your-app-path/app.py --server.address 0.0.0.0 --server.port 8501",
    interpreter: "none",
    env: {
      STREAMLIT_SERVER_HEADLESS: "true"
    }
  }]

}
```

## 3. Run PM2  (ออกจาก venv ด้วย)

```
cd your-app-path
pm2 start ecosystem.config.js
```

## 4. Check status (optinal)

```
pm2 list
pm2 log (app-id)
pm2 startup
pm2 save
```

# Congration 😊😊😊

<img width="941" height="371" alt="image" src="https://github.com/user-attachments/assets/6b2ce9e7-7e58-4c82-8445-0641ee51c950" />



