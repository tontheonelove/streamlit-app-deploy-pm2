# streamlit-app-deploy-pm2 💻


## โครงสร้างไฟล์ (ตัวอย่าง)

```
ic-billing-automate/
 ├── app.py
 ├── .env
 ├── requirements.txt
 └── ecosystem.config.js
```


## edit ecosystem.config.js

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
```
}



