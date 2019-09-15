engine='python'
import re
import pandas as pd
import numpy as np
import csv
import matplotlib.pyplot as plt
from zipfile import ZipFile
# this function is used for filter with only one key values
def searchWithOneKey(dataset):
 print("enter 1 if you want to search with IPADDRESS \nenter 2 if you want to search with
REQUEST_TYPE \nenter 3 if you want to search with STATUS_CODE.\nenter 4 if you want to search with
ERROR ")
 select = int(input("enter your choice"))
 if select==1:
 ipAddress=input("enter IPADDRESS for fillter=> ")
 p = dataset[(dataset['IP_ADDRESS'] == ipAddress)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==2:
 requestType=input("enter REQUEST_TYPE for fillter=> ")
 p = dataset[(dataset['REQUEST_TYPE'] == requestType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==3:
 statusCode=input("enter STATUS_CODE for fillter=> ")
 p = dataset[(dataset['STATUS_CODE'] == statusCode)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==4:
 errorType=input("enter ERRORTYPE for fillter=> ")
 p =dataset[(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()

 else:
 print("please inter valid operation")
 p.to_csv('log.csv',index=False)

# this function is used for filter with only one key values
def searchWithTwoKeys(dataset):
 print("enter 1 if you want to search with IPADDRESS AND ERROR. \nenter 2 if you want to search with
ERROR AND REQUEST_TYPE. \nenter 3 if you want search with REQUEST_TYPE AND STATUS_CODE.
\nenter 4 if you want search with IPADDRESS AND STATUS_CODE. \nenter 5 if you want search with
ERROR AND STATUS_CODE. \nenter 6 if you want to search with IPADDRESS AND REQUEST_TYPE.")
 select = int(input("enter your choice"))
 if select==1:
 ipAddress=input("enter IPADDRESS for fillter=> ")
 errorType=input("enter ERRORTYPE for fillter=> ")
 p = dataset[(dataset['IP_ADDRESS'] == ipAddress) &
(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==2:
 errorType=input("enter ERRORTYPE for fillter=> ")
 requestType=input("enter REQUEST_TYPE for fillter=> ")
 p = dataset[(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType) &
(dataset['REQUEST_TYPE'] == requestType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==3:
 requestType=input("enter REQUEST_TYPE for fillter=> ")
 statusCode=input("enter ERRORTYPE for fillter=> ")
 p = dataset[(dataset['STATUS_CODE'] == statusCode) & (dataset['REQUEST_TYPE'] == requestType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==4:
 ipAddress=input("enter IPADDRESS for fillter=> ")
 statusCode=input("enter ERRORTYPE for fillter=> ")
 p = dataset[(dataset['IP_ADDRESS'] == ipAddress) & (dataset['STATUS_CODE'] == statusCode)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==5:
 errorType=input("enter ERRORTYPE for fillter=>")
 statusCode=input("enter ERRORTYPE for fillter=>")
 p = dataset[(dataset['STATUS_CODE'] == statusCode) &
(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select == 6:
 ipAddress=input("enter IPADDRESS for fillter=>")
 requestType=input("enter REQUEST_TYPE for fillter=>")
 p = dataset[(dataset['IP_ADDRESS'] == ipAddress) & (dataset['REQUEST_TYPE'] == requestType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 else:
 print("plz choose the correct choice")

 p.to_csv('log.csv',index=False)


#this function defination for the filter logs with three key values
def searchWithThreeKeys(dataset):
 print("enter 1 if you want to search with IPADRESS AND ERROR AND REQUEST_TYPE.\nenter 2 if you
want to search with IPADDRESS AND REQUEST_TYPE AND STATUS_CODE. \nenter 3 if you want to
search with ERROR AND REQUEST_TYPE AND STATUS_CODE. \nenter 4 if you want to search with
IPADRESS AND ERROR AND STATUS_CODE")
 select = int(input("enter your choice"))
 if select==1:
 ipAddress=input("enter IPADDRESS for fillter=> ")
 errorType=input("enter ERRORTYPE for fillter=> ")
 requestType=input("enter REQUEST_TYPE for fillter=> ")
 p = dataset[(dataset['IP_ADDRESS'] == ipAddress) &
(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType) & (dataset['REQUEST_TYPE'] ==
requestType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==2:
 ipAddress=input("enter ERRORTYPE for fillter=> ")
 requestType=input("enter REQUEST_TYPE for fillter=> ")
 statusCode=input("enter ERRORTYPE for fillter=> ")
 p = dataset[(dataset['ERROR'] == ipAddress) & (dataset['REQUEST_TYPE'] == requestType) &
(dataset['STATUS_CODE'] == statusCode)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==3:
 errorType=input("enter ERRORTYPE for fillter=> ")
 requestType=input("enter REQUEST_TYPE for fillter=> ")
 statusCode=input("enter ERRORTYPE for fillter=> ")
 p = dataset[(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType) &
(dataset['STATUS_CODE'] == statusCode) & (dataset['REQUEST_TYPE'] == requestType)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 elif select==4:
 ipAddress=input("enter IPADDRESS for fillter=> ")
 errorType=input("enter ERRORTYPE for fillter=> ")
 statusCode=input("enter STATUS_CODE for fillter=> ")
 p=dataset[(dataset['IP_ADDRESS'] == ipAddress) &
(dataset['ERROR'].astype(str).str[:3].astype(np.str)== errorType) & (dataset['STATUS_CODE'] ==
statusCode)]
 p.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
 plt.show()
 else:
 print("please inter valid operation")
 p.to_csv('log.csv',index=False)

# initialize the column names for dataframes
l=['DATE-TIME','ERROR', 'IP_ADDRESS' ,'d','USER_AGENT','f', 'REQUEST_FROM', 'h',
'REQUEST_TYPE','j','API','l','USER_LOGIN', 'n' ,'USER_NAME','p','ENTERPRISE_ID', 'r',
'ENTERPRISE_NAME', 't','AUTH_STATUS','v','STATUS_CODE','x', 'RESPONSE_TIME' ,'z','A']
#main loop of the code
fileName =input("enter the file in zip format with .zip=> ")
with ZipFile(fileName, 'r') as zip:
 zip.extractall()
textFileName = fileName[:-4]+'.txt'
dataSet=pd.read_csv(textFileName,delimiter=",|=",names=l) #this line make the dataframe for test file
dataSet=dataSet.drop(columns=['d','f','h','j','l','n','p','r','t','v','x','z','A']) #this line for drop the
unnaccessary columns.
dataSet['ERROR']=dataSet['ERROR'].astype(str).str[:-10].astype(np.str) #For remove the extra line in
error_code
for j in ['DATETIME','ERROR','IP_ADDRESS','USER_AGENT','REQUEST_FROM','REQUEST_TYPE','API','USER_LOGIN','USE
R_NAME','ENTERPRISE_ID','ENTERPRISE_NAME','AUTH_STATUS','STATUS_CODE','RESPONSE_TIME']:
 dataSet[j]=dataSet[j].astype(str).str[:-1].astype(np.str) #remove the last # from the valuse of the keys
# group by plot the graph beteween request type and the user login how many users are request type is
post and how many users request type is get
dataSet.groupby(['REQUEST_TYPE','USER_LOGIN']).size().unstack().plot(kind='bar',stacked=True)
plt.show()
#loop for perform the filter as many times u want
print ("Do you want to search")
userChoice = input("Type Y/y for yes and N/n for No=> ")
while(userChoice == 'Y' or userChoice=='y'):
 print("\nselect 1 if you want with search with one key \nselect 2 if you want with search with two keys
\nselect 3 if you want with search with three keys")
 select =int(input())
 if select== 1:
 searchWithOneKey(dataSet)
 elif select==2:
 searchWithTwoKeys(dataSet)
 elif select== 3:
 searchWithThreeKeys(dataSet)
 print ("Do you want to search")
 userChoice = input("Type Y/y for yes and N/n for No=> ")


 
#error=input("ERROR")
#user_agent=input("ENTER USER-AGENT ")
#user_name=input("ENTER USER-NAME ")
#enterprise_id=int(input("ENTERPRISE-ID"))
