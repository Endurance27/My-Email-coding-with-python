# My-Email-coding-with-python

from email.message import EmailMessage
import ssl
import smtplib

sender_email = "endykay64@gmail.com"
email_password ="sikx kdsf ajry toxp"
receiver_email = [
  "acheampong6040@gmail.com",
  "hayod11623@cgbird.com"
]


subject = "Our love journey will always grow stronger"
body = '''
 Love Meeting Agenda

 Date: [12/06/2024]
 Time: [12:00]
 Venue: [legon city mall]


Opening Remarks
Welcome: A warm welcome to our special love meeting.
Purpose: To celebrate and cherish our love journey.

Agenda Items

1.Reflection on Our Love Journey
    Memories: Share favorite moments and memories that have brought us closer.
    Milestones: Highlight significant milestones we have achieved together.

2. Appreciation and Gratitude
   Express Gratitude: Take turns expressing gratitude for each others love, support, and companionship.
   Compliments: Share what we love and appreciate most about each other.

3.Commitment to Growth
   Growth Areas: Discuss areas where we can continue to grow individually and as a couple.
   Goals: Set new goals for our relationship to ensure continuous growth and deepening of our bond.

4. Love Affirmations
   Affirmation Exchange: Exchange affirmations that reinforce our commitment to each other.
   Promises: Make promises to support and cherish each other through all lifes adventures.

5. Future Plans
   Dreams and Aspirations: Share dreams and aspirations for our future together.
   Plans and Projects: Discuss upcoming plans and projects that excite us and bring us closer.

Closing Remarks
Summarize: Recap the key points discussed during the meeting.
Encouragement: Offer words of encouragement and love to continue nurturing our relationship.
Final Affirmation: Conclude with a final affirmation of our love and commitment.

Closing Affirmation
"Our love journey will always grow stronger. Together, we will face all challenges, celebrate all victories, and cherish every moment, making our bond unbreakable and everlasting."


Meeting Adjourned

Note: This meeting is a special moment to honor and celebrate our love. Let's cherish each other and continue building a beautiful journey together.

'''
em = EmailMessage()
em ['From'] = sender_email
em ['To'] = receiver_email
em ['subject'] = subject
em.set_content(body)
context= ssl.create_default_context()
with smtplib.SMTP_SSL("smtp.gmail.com" ,465, context=context)as smtp:
    smtp.login(sender_email,email_password)
    smtp.sendmail(sender_email,receiver_email,em.as_string())




