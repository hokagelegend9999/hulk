# GENOM SCRIPT VPS INSTALL


## 1. INSTALL 

```
wget https://github.com/hokagelegend9999/hulk/raw/refs/heads/main/hulk && chmod +x hulk && ./hulk
```

#### ALTERNATIF CERT :


```
DOMAIN="ISI SUBDOMAIN"
EMAIL="ISI EMAIL SUBDOMAIN"
/root/.acme.sh/acme.sh --set-default-ca --server zerossl && \
/root/.acme.sh/acme.sh --register-account -m "$EMAIL" --server zerossl && \
/root/.acme.sh/acme.sh --issue --standalone -d "$DOMAIN" -k ec-256 && \
/root/.acme.sh/acme.sh --installcert -d "$DOMAIN" \
  --fullchainpath /etc/xray/xray.crt \
  --keypath /etc/xray/xray.key \
  --ecc && \
chmod 600 /etc/xray/xray.key && \
systemctl restart nginx && \
systemctl restart xray

```
