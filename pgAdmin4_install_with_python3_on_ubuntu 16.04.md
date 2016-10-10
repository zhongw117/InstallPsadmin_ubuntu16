1. Get source pgAdmin4

        wget https://ftp.postgresql.org/pub/pgadmin3/pgadmin4/v1.0/source/pgadmin4-1.0.tar.gz

2. unpack pgadmin4-1.0.tar.gz in home dir

3. Install pip3
    
        apt install python3-pip

4. Install virtualenv
       
        pip3 install virtualenv

5. Create virtualenv
       
        virtualenv --system-site-packages --no-setuptools --python=python3.5 ~/py3-venv-pgadmin

6. Activate virtualenv
       
        cd ~/py3-venv-pgadmin/bin
        source activate

7. Check pip3
       
        which pip3
        ~/py3-venv-pgadmin/bin/pip3

8. Install libpq-dev
       
        apt install libpq-dev

9. Install requrements
       
        cd ~/pgadmin4-1.0
        pip3 install -r requirements_py3.txt

10. Install qt-sdk
       
        apt install qt-sdk

11. Build the runtime
    
        cd ~/pgadmin4-1.0/runtime
        qmake
        make

12. [For desktop deployment](https://www.pgadmin.org/docs4/dev/desktop_deployment.html)
        
        cd ~/pgadmin4-1.0/web
        touch config_local.py
        nano config_local.py
        SERVER_MODE = False
        python3 setup.py

13. Run pgAdmin4
        
        python3 pgAdmin4.py

14. Exit virtualenv
        
        deactivate

15. Remove qt-sdk
        
        apt purge qt-sdk