# saas,paas,iaas  [[3]](#3).

![securityTeacher](https://github.com/anindameister/cloudAWS/blob/main/snaps/7.PNG)

# What is an AMI ? 

1. Amazon Machine Image (AMI)

2. it provides the information required to launch an instance.

3. You must specify an AMI when you launch an instance. 

4. You can launch multiple instances from a single AMI when you need multiple instances with the same configuration.

5. You can use different AMIs to launch instances when you need instances with different configurations.

6. 

# load balancer

- A load balancer distributes incoming application traffic across multiple EC2 instances in multiple Availability Zones. 

- Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, scalable compute capacity in the cloud.

- Elastic Load Balancing detects unhealthy instances and routes traffic only to healthy instances. 

- Your load balancer serves as a single point of contact for clients.

# Create a load balancer (ELB) for your infrastructure.


# steps to get in

1. login

2. my classroom- go to classroom

3. status check fulfilled 2/2

4. putty ip, provides

5. under ssh, side bar, click that and just choose source

5. upload the file

6. ec2-user

7. launch apache aws
sudo service httpd start  

8. just go to the url 

ec2-54-88-137-51.compute-1.amazonaws.com

# create a bucket

1. mybucket17071988

2. click on the name, and just the name to upload

# project
###### lab3

- config [[1]](#1).
- before: config file

![config](https://github.com/anindameister/cloudAWS/blob/main/snaps/4.PNG)

- after: config file
- we want the output in table format

![config](https://github.com/anindameister/cloudAWS/blob/main/snaps/5.PNG)

- the below is done in anaconda, by just start-anaconda, did the below thing in the default directory. library has been gotten, and boto3 has been imported siccessfully without error
```
 pip install boto3
```

![pip install boto3](https://github.com/anindameister/cloudAWS/blob/main/snaps/6.PNG)

###### s3

- s3 is a simple storage service. S3 stores data and documents. it's like a storage device in your computer like a hdd.
- then there are many buckets
- buckets are like folders in the hdd
- in the buckets, we put a lot of documents.
- let's say that you have two types of docs: - images and pdfs. So we can create two buckets, one of which could containn all images and other one, all pdfs and non-image docs
- you can also put all the docs in a simgle bucket as well, but for simplicity we can keep docs separately in regards to category
- we can create bucket using the console, or cli, or boto3 python package
- before we get into that, we got to make sure that our credentials are perfectly in sync with the Aws', recall the problems
- gettingTheCurrentCredentials [[5]](#5).

![gettingTheCurrentCredentials](https://github.com/anindameister/cloudAWS/blob/main/snaps/9.PNG)

- boto3 way from laptop to create a bucket [[4]](#4).

![boto3 way from laptop to create a bucket](https://github.com/anindameister/cloudAWS/blob/main/snaps/8.PNG)

# AWS Tutorial - AWS SQS - Overview [[6]](#6).

####### sqs 

![amazon sqs](https://github.com/anindameister/cloudAWS/blob/main/snaps/10.PNG)

####### standard queue

![standard queue](https://github.com/anindameister/cloudAWS/blob/main/snaps/11.PNG)

- default queue- the default queue that's created is standard queue
- if a message is there in the queue, then it'd be delievered at-least once, could be more than once; but at-least once
- A sender of an asynchronous message continues to execute after sending the message, [[7]](#7).
- whereas a sender of a synchronous message waits until it receives a reply from the receiver that it has completed its processing of the message before continuing execution.
- this standard queue option is to be chosen, in regards to asynchronousity 

####### fifo queue

- it has all the capabilities of a standard queue

![fifo queue](https://github.com/anindameister/cloudAWS/blob/main/snaps/12.PNG)

###### amazon sqs architecture [[8]](#8).

![amazon sqs architecture](https://github.com/anindameister/cloudAWS/blob/main/snaps/13.PNG)

![amazon sqs architecture](https://github.com/anindameister/cloudAWS/blob/main/snaps/15.PNG)

######## What is Distributed Messaging System? [[9]](#9).
- Distributed messaging is based on the concept of reliable message queuing. 
- Messages are queued asynchronously between client applications and messaging systems. 
- A distributed messaging system provides the benefits of reliability, scalability, and persistence.

![Distributed Messaging System](https://github.com/anindameister/cloudAWS/blob/main/snaps/14.PNG)

####### sqs message lifecycle

![sqs message lifecycle](https://github.com/anindameister/cloudAWS/blob/main/snaps/16.PNG)

![sqs message lifecycle](https://github.com/anindameister/cloudAWS/blob/main/snaps/17.PNG)

####### what's message visibility timeout

![message visibility timeout](https://github.com/anindameister/cloudAWS/blob/main/snaps/18.PNG)

####### key points [[10]](#10).

![message visibility timeout](https://github.com/anindameister/cloudAWS/blob/main/snaps/19.PNG)

- https://console.aws.amazon.com/sqs/v2/home?region=us-east-1#/

```
myList=[]
for j in range(1,50):
  
  myList.append('a'*j)

myList[0]=0
myList[1]=1

response = queue.send_messages(Entries=[
    {
        'Id': '1',
        'MessageBody': "No. 1 from Fibonacci series is "+myList[0]
    },
    {
        'Id': '2',
        'MessageBody': 'No. 2 from Fibonacci series is ',+myList[1]

    },
    for i in range(2,len(myList)):
      myList[i]=myList[i-1]+myList[i-2]
      {'Id': i+1,'MessageBody': "No. 1 from Fibonacci series is "+myList[i]}])

```

## References
<a id="1">[1]</a> 
https://youtu.be/tW3HoYRnABs

<a id="2">[2]</a> 
https://youtu.be/qsPZL-0OIJg

<a id="3">[3]</a> 
file:///H:/security/clone/security/C2,WI-SSI-en.pdf

<a id="4">[4]</a> 
C:\aws\boto3WayFromLaptopToCreateAbucket.ipynb

<a id="5">[5]</a> 
https://drive.google.com/drive/folders/13AlfWRNk9tRJ7OXJon5x_U--zioc9GVJ

<a id="6">[6]</a> 
https://www.youtube.com/watch?v=_CsN94YlNjk

<a id="7">[7]</a> 
https://www.researchgate.net/publication/339124293_Difference_Between_Synchronous_and_Asynchronous_Messages_Synchronous_Messages#:~:text=A%20sender%20of%20an%20asynchronous,the%20message%20before%20continuing%20execution.

<a id="8">[8]</a> 
https://www.youtube.com/watch?v=K6Bao5WaPLU&list=PLrDJzKfz9AUvnUoCvwesGNaD55Wyljjzh&index=2&t=49s

<a id="9">[9]</a> 
https://www.tutorialspoint.com/apache_storm/apache_storm_distributed_messaging_system.htm#:~:text=What%20is%20Distributed%20Messaging%20System,reliability%2C%20scalability%2C%20and%20persistence.

<a id="10">[10]</a> 
https://www.youtube.com/watch?v=wDEnNFsPe0k&list=PLrDJzKfz9AUvnUoCvwesGNaD55Wyljjzh&index=3