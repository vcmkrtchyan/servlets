## Important things

### 1. Structure

```
.
├── pom.xml
└── src
    └── main
        ├── java
        │   └── am
        │       └── tech42
        │           └── HelloWorldServlet.java
        └── webapp
            └── WEB-INF
                └── web.xml
```

### 2. web.xml

Contains information about servlets and URL mappings

For example

```xml
<servlet>
    <servlet-name>hello-world</servlet-name>
    <servlet-class>am.tech42.HelloWorldServlet</servlet-class>
</servlet>

<servlet-mapping>
    <servlet-name>hello-world</servlet-name>
    <url-pattern>/hello</url-pattern>
</servlet-mapping>
```

### 3. Servlet classes

- Must extends HttpServlet to provide URL handling

For example, if we want to support GET method

```java
public class HelloWorldServlet extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        resp.getWriter().println("hello world");
    }

}
```

### 4. Set packaging to war

Add the following packaging to your pom.xml

```xml
<packaging>war</packaging>
```

### 5. Package with maven

```sh
mvn clean package
```

### 6. Copy the war directory(not the archive) to tomcat webapps folder

### 7. Profit!
