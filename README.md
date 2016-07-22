# ScotchBox 2.5 with CakePHP 2.8.5

To use another CakePHP 2.x version, modify the version number on line 14 of the Vagrantfile.
https://packagist.org/packages/cakephp/cakephp

Run `vagrant up` to install a Scotch/Box with CakePHP.
A folder `public` is created with a new CakePHP project, including a modified `config/app.php` to reflect default Scotch/Box MySQL settings.

Also fixes scotch/box UTF-8 bug.

Open <http:192.168.33.10/> in your browser to check if things work.


