```bash
python3 -m venv venv

source venv/bin/activate

docker-compose --project-name frappe --file docker-compose.yaml up --detach
docker-compose --project-name frappe --file docker-compose.yaml down

podman compose --project-name frappe --file docker-compose.yaml up --detach
podman compose --project-name frappe --file docker-compose.yaml down

# Delete voluumes also
podman compose --project-name frappe --file docker-compose.yaml down --volumes

# Delete voluumes and images also
podman compose --project-name frappe --file docker-compose.yaml down --volumes --rmi

# Logs

# Check running containers
podman container list

# Logs
podman container logs --tail=100 frappe_backend_1 > logs/frappe_backend_1_logs.txt 2>&1
```
