# Redis Adapter

### Group #8:  Jiawei Zhao & Yiqin Zhang



We created a web-based interface for the EC500 Redis server. The webpage consists of three parts:  



1. ##### First of all, set up the password. 

   

   We generated an md5 hash code with salt and password for security concerns. We asked users to input a random string as salt, concatenated it with the assigned password as the seed, and then called the md5 function imported from the `md5.min.js` to obtain a hashcode.



2. ##### The second step is to send requests to the Redis database. 

   After hashing the password, we constructed the URL to send the Get request, which composes the Redis server address, the salt user entered, the hash string just produced, and the command message the user sent to the server, such as 

```javascript
"https://agile.bu.edu/ec500_scripts/redis.php?" + "salt=" + salt + "&hash=" + HashString + "&message=" + message
```

​		And then, we use ` XMLHttpRequest` to interact with the Redis server. 



3. ##### Lastly, display the data retrieved from the Redis server.

   After getting the response from the server,  we showed the fetched data on the webpage. Meanwhile, add an event listener to control the time to display the information.