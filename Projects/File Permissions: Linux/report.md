# File Permissions: Linux report

## Summary
I completed this project as part of the Google Cybersecurity Professional Certificate course.

This project involved examining the existing permissions in a fictional large organisations file system. I modified file and directory permissions to ensure they aligned with the organisation's security policies. I did this through the use of Linux commands. 

## Reviewing existing permissions
My task was to review the permissions in the ```projects``` directory of the file system. To navigate to the directory from the root directory, I used ```cd projects```. 

Once in the projects directory, I used the ```ls -la``` command. This displayed all the existing permissions for all the files and directories within the projects directory, including hidden files.

## How permissions are represented in Linux
Permissions in Linux are represented as a 10-character string. Each character in this string can be deconstructed:
The 1st character is either a ```d``` or a hyphen ```(-)```. It represents the file type. ```d``` represents a directory, whilst a hyphen ```(-)``` represents a regular file.

The remaining 9 characters are then represented as 3 groups, user, group and other. Within these groups the characters can either be read ```(r)```, write ```(w)``` and execute ```(x)```. These indicate the specific permissions the group has. 

Example: ```-rwxrw-r--```
The above example shows that these are the permissions for a regular file. The user has got read, write and execute permissions as seen with the first 3 characters, the group has read and write permissions and other has only read permissions. Absent permissions are represented as a hyphen ```(-)``` 

## Modifying file permissions
The research team for the organisation had recently archived a file called ```project_x.txt```. As a result, they didn't want anyone to have write permissions, but wanted the user and group to have read permissions.

To update the permissions, I used:
```chmod u-w,g-w,g+r .project_x.txt```

This command updated the permissions to remove write permissions from the user and group, and then add read permissions to the group. The user already had read permissions set. The period ```(.)``` is used when a file is marked as hidden.

## Changing directory permissions
As per organisation policy, the user ```researcher2``` is the only person that should have access to the ```drafts``` directory. Previously, the group had execute permissions for this directory, indicating that they were able to access the directory and its contents. 

To remove the group execute permissions I used:
```chmod g-x drafts```. 

## Benefits of modifying file permissions
By modifying the file permissions of the projects directory, the principle of least privilege was applied. This meant that users only had the minimum permissions required to perform their tasks.

As a result, the likelihood of the following has been reduced:
- Unauthorised file modification
- Accidental modification
- Insider threats
- Data exposure

## Reflection
This project has allowed me to strengthen my understanding of Linux commands such as ```ls -la``` and  ```chmod``` and how they are used by organisations to manage user permissions. It has also shown me the importance of updating permissions to ensure that systems remain secure.
