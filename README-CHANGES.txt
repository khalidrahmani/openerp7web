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
yahya@yahya:/opt/openerp$ sudo cp -R ~/Desktop/Aptana_Rails/workspace/openerp7/mrp_repair/ server/openerp/addons/
sudo /etc/init.d/openerp-server restart