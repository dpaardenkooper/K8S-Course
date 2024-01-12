Create serviceaccount
- kubectl create sa accessor
- kubectl create token accessor

Check token
- check jwt.io >> copy content token

Create pod manifestfile
- kubectl run accessor --image=nginx -oyaml --dry-run=client > pod.yaml
- add serviceaccount

Create pod
- kubectl create -f pod.yaml

Check mount
- kubectl exec -it accessor -- bash
- mount | grep serviceaccount

Check the content
- cd <path>
- ls
- <check if the files are there>

Check if you can get response of API
- env | grep KUBER
- https://<IP>

Recheck with token
- https://<IP> -k -H "Authorization: Bearer $(cat token)"
