TwitOff Python Files

Windows 10 commands

set FLASK_APP=twitoff:APP

flask run

flask shell

from twitoff.models import *

from twitoff.models import User

Example Code:

DB.drop_all()
DB.create_all()
u1 = User(name = 'austen')
t1 = Tweet(text = 'Lambda School Rocks!')
t2 = Tweet(text = 'Lambda School Rules!')
t3 = Tweet(text = 'Lambda School Crushes!')
u1.tweets.append(t1)
u1.tweets.append(t2)
u1.tweets.append(t3)
u1.tweets

u2 = User(name = 'jack')
t4 = Tweet(text = 'Twitter Rocks!')
t5 = Tweet(text = 'Twitter Rules!')
t6 = Tweet(text = 'Twitter Crushes!')
u2.tweets.append(t4)
u2.tweets.append(t5)
u2.tweets.append(t6)
u2.tweets

DB.session.add(u1)
DB.session.add(t1)
DB.session.add(t2)
DB.session.add(t3)
DB.session.add(u2)
DB.session.add(t4)
DB.session.add(t5)
DB.session.add(t6)

DB.session.commit()

u1 = User.query.filter(User.name == 'austen').first()
u1.tweets
u2 = User.query.filter(User.name == 'jack').first()
u2.tweets