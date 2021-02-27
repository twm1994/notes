create file
```sh
touch file_name
touch prefix{name_list}.suffix
touch prefix{start..end}.suffix
mkdir -p father/son/grandson
```

copy file/dir
```sh
cp file dir
cp -r ori_dir des_dir
```

remove file/dir
```sh
rm [-f] file
rm -r dir
mv file dir
mv ori_name new_name
```

view file
```sh
cat | sort
tac
nl -b [atn] -n [ln rn rz] -w
more
less
head
tail
file

ls
man
```

user & group management
```sh
su -l
sudo adduser
useradd
sudo addgroup
groupadd
usermod -G
sudo deluser  --remove-home
sudo chown
chmod [ugo][[+-][rw]]
sudo useradd -m -d /home/user1 -G group1,group2 -s /bin/sh user1
```

variable
```sh
declare VARNAME
echo $VARNAME
```

add path
`$PATH=$PATH:PATHNAME`

search
```sh
where
locate
which
find DIR -name DIRORFILE
```

[special characters]https://www.howtogeek.com/439199/15-special-characters-you-need-to-know-for-bash/(https://www.howtogeek.com/439199/15-special-characters-you-need-to-know-for-bash/)
```sh
/
.
..
~
#
?
*
;
[]
&
$
~
!
!!
<
|

```
