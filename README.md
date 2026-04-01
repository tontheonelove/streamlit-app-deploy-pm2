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
cd  your-app-path
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```


## 2. edit ecosystem.config.js

```
module.exports = {
  apps: [{
    name: "ic-billing-app",
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



