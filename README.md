**EMail-Client trying to replicate the Hey.com behavior with IMAP services that have support for sieve filters**

# Approach 

Decouple from the typical email folder style view to special views for each UX case and hide/automate all the email filter stuff under a opinonated UX approach.
Using the points mentioned here https://firesofmay.substack.com/p/hey-app-review-a-personal-take

* Screener
  * Move all emails to a imap folder with a filter
  * if screened out - make a blacklist for this email -> gone
  * if screened in - do a filter to move all future mails to one of the three categories, move all existing mails from the screener accordingly
  * The user will propably handle all screener mails but if nothing is decided delete after certain amount of days
* 3 Kind of emails. Important, Feed, Paper Trail
* Important category (The inbox in IMAP)
  * Unread at first
  * Then two approaches possible
    * Read means nothing is done, leave it in the inbox - it is the read later stack. 
    * If you done - archive it. Move it out of the Inbox folder
    - Or
    * Read means nothing is done, all mails in the inbox.
    * Somehow marked (Star?) if it's the read later stack
  * Set aside - some imap tag on it that it can be presented 
  
* Feed and Paper Trail 
  * have no unread/read status and moved with filters to imap folders
  * If you move a address to these categories - add filters and move all emails to the corresponding folders
  * Emails will be presented in a feed like view
  
* Contact Page
  * Show a contact page, with all mails, categorisation, attachments and so on
  * If you change category move and adapt filters
  * Show extracted email signature

* Helpful stuff
  * Rename email threads -> possible with IMAP
  * Not sure if merging is possible -> TODO check
  * Notification are Opt-in for all except the Important category
  * Replace a too big attachment with a link and upload it to some service - Call a script standard https://transfer.sh/ but so can be customized
  * Check if it's is possible to replicate a note feature. Usecase. Email thread -> Phone Conversation -> Add notes to the corresponding topic
  * Maybe get rid of email signatures in threads - https://github.com/mailgun/talon
  * https://github.com/yourtempo/tempo-quill-icons

* Technology
  * Just using evolution data server or if cross platform https://github.com/notpushkin/Mailspring-Libre ?
    * https://github.com/elementary/mail
    * https://github.com/matzipan/envoyer
  * Additional **filter rules of the mail provider must be changeable per IMAP**. 
  * Sieve Filter
    * https://www.heise.de/netze/rfc/rfcs/rfc5804.shtml
    * https://github.com/thsmi/sieve
    * https://www.systutorials.com/docs/linux/man/1-sieve-filter/
    * http://manpages.ubuntu.com/manpages/eoan/en/man1/sieve-connect.1.html
    * https://gitlab.com/htgoebel/managesieve
  * If it's feasible to use a Trackingpixel blocker, do it. List from hey.com https://gist.github.com/dhh/360f4dc7ddbce786f8e82b97cdad9d20
  Use adblocker like feature in webkit
  Maybe something like https://github.com/stefanXO/PixelBlock
  https://github.com/OneClickLab/ugly-email-trackers
  
* Behavior in other clients (mobil)
  * Important will be the normal Inbox just like today
  * Feed and Paper trail will be moved to folders and must be activly opened. Since these mails are not time relevant this is just fine.
  * Screened out mails will not hit the mailbox
  * Not Screened in mail will not hit the inbox and stored for review later
  * So it improves the experience with normal approach IMAP clients.


TODO Should some ux from tempo included? https://www.yourtempo.co/
