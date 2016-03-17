# scotch/box with CakePHP

Run `vagrant up` to install a Scotch/Box with a fresh CakePHP project in `/home/vagrant/cakephp-project`.

A soft link to `/var/www/public` is created which points to this CakePHP project.

A modified `app.php` is copied to `config/app.php` to reflect default Scotch/Box MySQL settings.

Also fixes scotch/box UTF-8 bug.

Open <http:192.168.33.10/> in your browser to check if things work.


