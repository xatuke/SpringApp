# SpringApp
A web-app which supports CRUD operations.

[Youtube](https://youtu.be/89bYHjauJs8)

## Instructions to use:
### Database
Use the following script to make the data base:
```
CREATE DATABASE `springapp`;
CREATE TABLE  `springapp`.`users` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `firstname` varchar(45) NOT NULL DEFAULT '',
  `lastname` varchar(100) NOT NULL DEFAULT '',
  `address` varchar(100) NOT NULL DEFAULT '',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;
```

### Server
I've used Tomcat Apache server (version: 9.0.13)
After connecting the project to the server, in `the server.xml` file find:
```
<Context docBase="SpringApp" path="/SpringApp" reloadable="true" source="org.eclipse.jst.jee.server:SpringApp" />
```

and replace it with:

```
<Context docBase="<Project Folder Location>\SpringApp\target\SpringApp-0.0.1-SNAPSHOT\" path="/SpringApp" reloadable="true" >
        <Resource 
                    name="jdbc/springmvc" 
                    auth="Container" 
                    type="javax.sql.DataSource"
                    username="root" 
                     password="<password of your mysql>" 
                     driverClassName="com.mysql.jdbc.Driver"
                     url="jdbc:mysql://localhost:3306/springapp"
                     maxActive="5" 
                     maxIdle="3" 
                      />
</Context>

```
After completing the above steps, you're good to go after starting the server, go to: `http://localhost:8080/SpringApp/user/list` on your browser.

## Screenshots
![img1](https://i.imgur.com/tqwBr3l.png)
![img2](https://i.imgur.com/mAxOaJc.png)
![img3](https://i.imgur.com/dLnXyZE.png)
