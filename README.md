
#  Upload file

+ user lose connection during upload of file.

+ very slow uploading. How server will handle situation that user will be uploading file for many hours.

+ we want to send file with the same name second time. Can server handle such situation?

+ what will happened if user will send very big file. Imagine file that have size in gigabytes/terabytes.

+ what will happened if user will provide path to multiple files? Something like this _"C:\catalog\file1.html" "C:\catalog\file2.pdf"_

+ what will happened if user will start uploading from two browsers in the same file.

+ what will happened if user will provide file with japanese or arabic signs in path?



# Show error message:

+ we should not show path to file on our server. Only simple error message should be shown.

+ we shound not provide anyting in URL param. There should be no URL params for example indicating where we wanted to put file in our file structure (path to such file)

+ how we generate error message. Can end user find what tools are we using (version of system / file system etc.)? We shoud not show such info to end user.



# File with virus:

+ try to use files that contain virus. Do we detect such files in any way? 

# Detecting HTML:

+ how we are detecting valid HTML? Is it possible to put inside some scripts? This scritps will be run on server side?  

+ What will happened if user manually will change extension of file from html to pdf/pdf to html?

+ What will happened if user manually will change extension of file from html or pdf to jpg or from jpg to html or pdf. (instead of jpg there can be other common used extension).

+ What will happened if user manually will change extension of file from html or pdf to exe or from exe to html or pdf.

+ File without content. How system will handle situation if file is empty.

+ If we validate by extension - what will happend if user will provide file without extension.

+ Corrupted file - how system will handle it?

# Problems with system:

+ what will happened if storage drive is full (depends if this is handled by this team or in this story)

# Scaling:

+ how we are handling situation that we have more than one database server? How such system sohuld be changed if we will add many more servers?

+ how system will handle situation that files will be uploaded by many users? (depends on expected traffic - 10 users or 1 000 000 users daily). Imagine that there will be more than "safe" number of users. How system will react?

# Publish file:

+ do we want to have files acessible for end user by path on our server? What will happened if we will have more servers / databases with files - can our system handle this?

# Send notification:

+ we should not provide info about file path

