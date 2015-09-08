<p><div><img src="https://jurisdesk.com/wp-content/uploads/2015/07/j25k1-temp.png" alt="Jurisdesk LLC Logo" align="right"/></div><br><p>
**What is Freedoms?**

- Freedoms is a python tool, based off of easy engine by RTcamp.  I'm not taking credit for this.  I'm making a few tweeks that I personally need, and I believe will be beneficial to others. If you need help once the project is done, we offer free support at https://jurisdesk.com/support/.  No catch at all..100% free but we accept donations.  Please wait until this file states that Freedoms is production ready before implementing. </p></li>

- We welcome collaborators, in fact we need them!  If you love wordpress, and you love what easy engine by RTcamp does, but wish for a tad more "Freedoms", just hop on board and let's code them in! RTcamp has been my unspoken mentor and my teams unspoken mentor. Indirectly through studying their configuration, Jurisdesk.com and nginxhosting.co have designed a plan to kick it up a notch.  

- We need collaboration! Two is better than one - Many folks is better than two.  Freedoms, just like easy engine, will make it super simple to manage your wordpress sites running on an nginx web-server. Furthermore one item on the roadmap is drupal - Recently I started playing with it, and honestly I love it.  Also on the roadmap is a centos version as it is much needed. </p></li>

- The centos options are rather complex if your just starting your coding journey. However the best way to learn is to DO.  I wanna give a shout out to digitalocean.com - the number one cloud computing provider.  Don't listen to what people say, it's because they are scared by the command line.  Hopefully this tool will help you learn.  Study the configurations.  Ask questions, learn!  NGINX is powerful. </p> </div>

**Roadmap for Supported Distros - Under Development:**

- Ubuntu 12.04 & 14.04
- Debian 7 & 8
- Centos 7
- Ubuntu 15.04
- Centos 6

**Port Requisites:**
- 22/TCP (Inbound/Outbound) : Standard SSH port
- 80/TCP (Inbound/Outbound) : Standard HTTP port
- 443/TCP(Inbound/Outbound) : Standard HTTPS port
- 11371/TCP (Outbound)      : To connect to GPG Key Server
- Secure your admin area - if you use ssl stapling and don't have a wildcard cert, we plan on keeping all admin tools on a subdirectory rather than a port. 

## Quick Start

```bash
wget -qO freedoms freedoms.cx/jd && sudo bash freedoms     # Install LEMP Stack - with a boatload of additional options.  Configure your static html site or wordpress.  Freedoms makes it simple to create virtual hosts, and configures nginx and the options you choose.  Pagespeed, HHVM, Redis, and/or fcgi, scgi, and uwsgi. 

Be careful!  A good config is hhvm and pagespeed or hhvm and redis.  Redis is wonderful if you want to scale out and make your site highly available as it is based off key value pairs and caches objects - think about the possibilities!  Redis and NGINX plus servers worldwide with Redis and NGINX. 

A simple example of the creation of a wordpress site is:

sudo freedoms site create example.com --wp     # Install required packages & setup WordPress on example.com
```

## Update Freedoms


Update procedure for Freedoms to latest version

#### For current installed version prior to 3.0.6
```bash
wget -qO freedoms freedoms.cx/jd && sudo bash freedoms

```
#### If current version is after than 3.0.6
```
freedoms update
```

## More Site Creation Commands

### Standard WordPress Sites

```bash
freedoms site create example.com --wp                  # install wordpress without any page caching
freedoms site create example.com --w3tc                # install wordpress with w3-total-cache plugin
freedoms site create example.com --wpsc                # install wordpress with wp-super-cache plugin
freedoms site create example.com --wpfc                # install wordpress + nginx fastcgi_cache
freedoms site create example.com --wpredis             # install wordpress + nginx redis_cache
```

### WordPress Multsite with subdirectory

```bash
freedoms site create example.com --wpsubdir            # install wpmu-subdirectory without any page caching
freedoms site create example.com --wpsubdir --w3tc     # install wpmu-subdirectory with w3-total-cache plugin
freedoms site create example.com --wpsubdir --wpsc     # install wpmu-subdirectory with wp-super-cache plugin
freedoms site create example.com --wpsubdir --wpfc     # install wpmu-subdirectory + nginx fastcgi_cache
freedoms site create example.com --wpsubdir --wpredis  # install wpmu-subdirectory + nginx redis_cache
```

### WordPress Multsite with subdomain

```bash
freedoms site create example.com --wpsubdomain            # install wpmu-subdomain without any page caching
freedoms site create example.com --wpsubdomain --w3tc     # install wpmu-subdomain with w3-total-cache plugin
freedoms site create example.com --wpsubdomain --wpsc     # install wpmu-subdomain with wp-super-cache plugin
freedoms site create example.com --wpsubdomain --wpfc     # install wpmu-subdomain + nginx fastcgi_cache
freedoms site create example.com --wpsubdomain --wpredis  # install wpmu-subdomain + nginx redis_cache
```

### Non-WordPress Sites
```bash
freedoms site create example.com --html     # create example.com for static/html sites
freedoms site create example.com --php      # create example.com with php support
freedoms site create example.com --mysql    # create example.com with php & mysql support
```

### HHVM Enabled Sites
```bash
freedoms site create example.com --wp --hhvm           # create example.com WordPress site with HHVM support
freedoms site create example.com --php --hhvm          # create example.com php site with HHVM support
```

### PageSpeed Enabled Sites
```bash
freedoms site create example.com --wp --pagespeed      # create example.com WordPress site with PageSpeed support
freedoms site create example.com --php --pagespeed     # create example.com php site with PageSpeed support
```

## Planned Stack Options - Site creation


|                    |  Single Site  | 	Multisite w/ Subdir  |	Multisite w/ Subdom     |
|--------------------|---------------|-----------------------|--------------------------|
| **NO Cache**       |  --wp         |	--wpsubdir           |	--wpsubdomain           |
| **WP Super Cache** |	--wpsc       |	--wpsubdir --wpsc    |  --wpsubdomain --wpsc    |
| **W3 Total Cache** |  --w3tc       |	--wpsubdir --w3tc    |  --wpsubdomain --w3tc    |
| **Nginx cache**    |  --wpfc       |  --wpsubdir --wpfc    |  --wpsubdomain --wpfc    |
| **Redis cache**    |  --wpredis    |  --wpsubdir --wpredis |  --wpsubdomain --wpredis |

## Useful Links
- [Documentation] (http://nginx.org/wiki)
- [FAQ] (http://jurisdesk.com/freedoms/faq/)
- [Structure used] (http://jurisdesk.com/freedoms/structure/)
- [Free Support] (https://jurisdesk.com/support/)
- WE DO NOT OFFER PREMIUM SUPPORT - Wordpress started out free - Jurisdesk.com firmly believes in keeping it that way and keeping opensource welll....opensource!  
## We do accept Donations

<form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
<input type="hidden" name="cmd" value="_s-xclick">
<input type="hidden" name="hosted_button_id" value="Y8VRRKLAGNC2U">
<input type="image" src="https://flic.kr/p/yob6D2" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
<img alt="" border="0" src="https://www.paypalobjects.com/en_US/i/scr/pixel.gif" width="1" height="1">
</form>



## Careers

We are looking for [Python Developers]. Come on over to (https://jurisdesk.com/forums/careers/) to join our team. We need creatives and bloggers too!  Why python?  Well simply put it rocks, it's simple, and can do anything.  Forget ruby, forget php, python is the future. 

Work virtually - I'm sure you already do :-) 

During development, if you have any questions at all about setting up nginx, come on down to our support forums (https://jurisdesk.com/forums/support/) - We will never ever charge for helping another person!

---

## License
[GNU] Opensource Stack Development
