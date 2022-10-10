prepare the environment
=========
create a python3 virutal env and start using it:
```
python3 -m venv ~/venv/csf-s1
source ~/venv/csf-s1/bin/activate
```

install requirements
```
python3 -m pip install -r requirements.txt
```

start the deployment
```
python3 deploy.py -u <username> -p <password> -j <region> -r <resource group>
```


tests
=========
*step 1* launch the exploit with only WAF inline

```
python3 ./launch_attack_vector.py -c native
python3 ./send_command.py -c "netstat -tn 2>/dev/null |grep :443"
```

*step 2* launch the exploit with PANOS inline
```
python3 ./launch_attack_vector.py -c panos
python3 ./send_command.py -c "netstat -tn 2>/dev/null |grep :443"
```


cleanup the lab
=========
```
python3 ./destroy.py 
deactivate
```
