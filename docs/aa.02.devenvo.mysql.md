`Sunday, July, 14 2019`

**`12:04`**

dBMS utama adalah MySQL. Lingkungan luar dari EHR yang akan dibangun kebanyakan masih
menggunakan relational database management system.

Penggunaan engine tipe ini tidak merupakan harga mati. Jika pada masa pengembangan mengharuskan adanya
tambahan mesin lain sebagai co-engine atau bahkan kemudian menggantikannya secara menyeluruh,
kemungkinan ini tidak ditutup.

Saat ini, tools yang saya gunakan untuk ber-kontak langsung dengan MySQL adalah MySQL Workbench. 

Perkara database schemma, mulai dari design sampai ke implementasinya akan didokumentasikan secara gradual dan dalam satu alur dengan dokumentasi untuk REST-nya sendiri.

Berikut adalah MySQL berikut peralatannya yang installed

```bash
$ mysql -V
mysql  Ver 14.14 Distrib 5.5.62, for debian-linux-gnu (x86_64) using readline 6.3

$ cat /etc/mysql/my.cnf | grep port
# One can use all long options that the program supports.
# It has been reported that passwords should be enclosed with ticks/quotes
port		= 3306
port		= 3306

$ mysql-workbench --version
MySQL Workbench CE (GPL) 6.0.8 11354  build 833
```

Berikut adalah dokumen instalasi yang sebelumnya telah dilakukan.

## MySQL Server

Sumber: https://support.rackspace.com/how-to/installing-mysql-server-on-ubuntu/

```bash
$ sudo apt-get update
$ sudo apt-get install mysql-server
```

## MySQL Client & MySQL-Workbench

Untuk client

Sumber: https://askubuntu.com/questions/489354/how-to-install-mysql-mysql-workbench-on-ubuntu-14-04

```bash
$ sudo apt-get install mysql-client
$ sudo apt-get install mysql-workbench
```

## Nodemon

Untuk membantu NodeJS, ditanam `nodemon`.

Sumber: https://www.npmjs.com/package/nodemon

```bash
$ npm install -g nodemon
```

Ada issue saat mencoba `nodemon`!.

```bash
[nodemon] Internal watch failed: watch ENOSPC
```

resolver: https://github.com/remy/nodemon/issues/907

```bash
$ echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```
`Sunday, July, 14 2019`

**`12:16`**