## How to run jupyter on a remote machine (SSH) and work on your local machine via SSH tunneling

1. log in your remote session via SSH
```
ssh <your_username>@<remote_server>
```

**on your remote machine**
2. go to your code folder and activate your conda environment
```
conda activate <your_env_name>
```

3. run jupyter on a specific port, like 1234
```
jupyter notebook --no-browser --port 1234
```

jupyter will give you a link like
```
http://localhost:1234/?token=asd231fe875a9a123121312f123127638130adsan1
```
copy it for later

**on your local machine**
4. open a SSH connection using port forwarding (tunneling)
```
ssh -NL 1234:localhost:1234 <your_username>@<remote_server>
```
(the shell will hang after you run this)

5. open your browser and paste the link to the jupyter notebook.

If you save the notebook, it will be saved on your remote machine.

You should also be able to do other operation on your remote machine (i.e. download files, or run shell commands, like ```!ls```).

Happy working!
