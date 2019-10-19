If you have only 1024 MB RAM, you may need at least 2048 MB swap.

```bash
sudo fallocate -l 2G /swapfile && \
sudo chmod 600 /swapfile && \
ls -lh /swapfile | grep -e "-rw-------" && \
sudo mkswap /swapfile && \
sudo swapon /swapfile && \
sudo swapon --show && \
sudo cp /etc/fstab /etc/fstab.bak && \
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```
