# flaskr

```
python3 -m venv ./venv

source ./venv/bin/activate

python3 -m pip install -r requirements.txt


# init database
FLASK_APP=flaskr FLASK_ENV=development flask init-db

# run flask in development mode
FLASK_APP=flaskr FLASK_ENV=development flask run

# create namespace
kubectl create ns flaskr

# imagePullSecret
ACCESS_TOKEN="..."

kubectl create secret docker-registry regcred \
    --docker-server=https://index.docker.io/v1/ \
    --docker-username=deepvoid \
    --docker-password=$ACCESS_TOKEN \
    -n flaskr

# verify secret
kubectl get secret -n flaskr

# deploy app
kubectl apply -f manifests/ -n flaskr

# verify ingress
kubectl get ing -n flaskr

# verify tls certificate
kubectl get cert -n flaskr





```
