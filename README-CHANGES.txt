To disable Messaging : 
create a nobody group and goto Setting > Technical > User Interface > menu , set menu group to nobody group
""""""
add 
div.oe_chatter{
  display: none;
}
.openerp .oe_topbar_item.oe_topbar_compose_full_email button{
  display: none; 
}
in openerp7/web/static/src/css/base.css  
""""
change  <td colspan="2" class="announcement_bar" style="display: none;"> in : openerp7/mail/static/src/xml/announcement.xml
"""""""""
remove            <div class="oe_footer">
                    Powered by <a href="http://www.openerp.com" target="_blank"><span>OpenERP</span></a>
                   </div>
openerp7/web/static/src/xml/base.xml

""""""""
update server with changes :
yahya@yahya:~$ sudo cp -R ~/Desktop/Aptana_Rails/workspace/openerp7/mrp_repair/ /opt/openerp/server/openerp/addons/
sudo /etc/init.d/openerp-server restart


#### Dropbox Database Backup 

installation 
$ cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -
$ ~/.dropbox-dist/dropboxd

yahya@yahya:~$ sudo touch /etc/init.d/dropbox
yahya@yahya:~$ sudo vim /etc/init.d/dropbox  # replace user yahya with nurwagen
sudo chmod +x /etc/init.d/dropbox
sudo update-rc.d dropbox defaults

yahya@yahya:~/Dropbox/PSQLBackup$ pg_dump -Fc nurwagen > backup

yahya@yahya:~/Dropbox/PSQLBackup$ sudo su - postgres

postgres@yahya:~$ psql

DROP DATABASE nurwagen;

CREATE DATABASE nurwagen WITH OWNER = openerp ENCODING = 'UTF8' TABLESPACE = pg_default LC_COLLATE = 'en_US.UTF-8' LC_CTYPE = 'en_US.UTF-8' CONNECTION LIMIT = -1;

yahya@yahya:~/Dropbox/PSQLBackup$ pg_restore -d nurwagen backup

#### Dropbox Database Backup 

need ~/.pgpass file with 
	localhost:5432:*:postgres:yahya
	127.0.0.1:5432:*:yahya:yahya
#### Dropbox Database Backup 

