Project
=======

Mysite Backend

## Installation

1. Download source of the backend system

		# configure git if not configured
		git config --global user.name "<your full name>"
		git config --global user.email <your email>
		git config --global core.editor vim
		# choose whatever name you like
		mkdir github
		cd github
		git clone git@github.com:i-mrhuanghs/mysite.git


2. Create mysql user and database

		# the user can create new
		mysql> create database mysite;
        mysql> source mysite/sql/mysite.sql;

        # the superuser has been created
        # Its account password is as follows
                username:admin
                password: 123456


3. Configure the backend system

	* Create local_settings.py

			cd github/mysite/project
			cp local_settings.py.example ../local_settings.py

	Update database configuration

		Comment out all statements in local_settings.py and then add the following to it.
		This is based on the 'DATABASES' in settings.py in the same directory.

			DATABASES['default']['HOST'] = 'localhost'
			DATABASES['default']['NAME'] = 'mysite'
			DATABASES['default']['USER'] = 'root'
			DATABASES['default']['PASSWORD'] = ''


4. Set up Python virtual environment

	A virtual environment has its own site directories, optionally isolated from system site directories.
	It also has its own Python binary and can have its own independent set of installed Python packages in its site directories.

			cd github/mysite
			# create the virtual environment
			python3 -m venv venv
    		# activate the virtual environment
    		# in mac
			source gitlab/mysite/bin/activate
            	# in windows
            	./venv/Script/activate.ps1
    		# install necessary dependencies, especially Django
    		for dev environment：pip install -r requirements-base.txt
    		# quit the virtual environment
    		deactivate


5. Run the backend system

	* Activate the virtual environment

			cd github/mysite
            # in mac
			source gitlab/mysite/bin/activate
            # in windows
            ./venv/Script/activate.ps1


	* Initialize or update the database

			./manage.py migrate



	* Start the backend system

			./manage.py runserver

