**EMail-Client trying to replicate the Hey.com behavior on IMAP service over something like OX (openXchange - used by a lot of email providers)**

# Approach 

Decouple from the typical email folder style view to special views for each UX case and hide/automate all the email filter stuff under a opinonated UX approach.
Using the points mentioned here https://firesofmay.substack.com/p/hey-app-review-a-personal-take

* Screener
  * Move all emails to a imap folder with a filter
  * if screened out - make a blacklist for this email -> gone
  * if screened in - do a filter to move all future mails to one of the three categories, move all existing mails from the screener accordingly
  * The user will propably handle all screener mails but if not nothing decided delete after certain amount of days
* 3 Kind of emails. Important, Feed, Paper Trail
* Important category (The inbox in imap)
  * Unread at first
  * Then two approaches possible
    * Read means nothing is done, leave it in the inbox - it is the read later stack. 
    * If you done - archive it. Move it out of the Inbox folder
    * Or
    * Read means nothing is done, all mails in the inbox.
    * Somehow marked (Star?) if it's the read later stack
  * Set aside - some imap tag on it that it can be presented 
  
* Feed and Paper Trail 
  * have no unread/read status and moved with filters to imap folders
  * If you move a address to these categories - add filters and move all emails from the inbox to the corresponding folders
  
* Contact Page
  * Show a contact page, with all mails, categorisation, attachments and so on
  * If you change category move and adapt filters
  * Show extracted email signature

* Helpful stuff
  * Rename email threads -> possible with IMAP
  * Not sure if merging is possible -> TODO
  * Notification are Opt-in for all except the Important category
  * Replace a to big attachment with a link and upload it to some service - Call a script standard https://transfer.sh/ but so can be customized
  * Check if it's is possible to replicate a note feature. Usecase. Email thread -> Phone Conversation -> Add notes to the corresponding topic
  * Get rid of those annoying email signatures in threads - https://github.com/mailgun/talon

* Technology
  * Just using evolution data server or https://github.com/jstedfast/MailKit if I do windows - gives all imap stuff.
  * Additional must be the **filter rules of the mail provider be changeable per IMAP**. Possible with OX and will be target. 
  https://tools.ietf.org/html/rfc5466#section-3.2 
  https://kb.mailbox.org/m/mobile.action#page/1181544
  * If it's feasible to use a Trackingpixel blocker do it. Maybe something like https://github.com/stefanXO/PixelBlock - Investigate
