# Level 14

http://natas14.natas.labs.overthewire.org

![](assets/natas14.png)

Clicking on 'View sourcecode' brings us to the following code.

![](assets/natas14-solution-1.png)

Since there is an SQL query being executed, we can probably utilise an SQL injection attack. Trying the standard payload of `admin` with `" or 1=1` doesn't work as the second half of that statement gets interpreted as PHP.

![](assets/natas14-solution-2.png)

However, if we comment out the rest with `#`, we get a successful login.

![](assets/natas14-solution-3.png)

This attack could have been prevented by using parameterised queries and sanitising user input. As mentioned in the lectures, it is a bad idea to mix user-supplied data with code.
