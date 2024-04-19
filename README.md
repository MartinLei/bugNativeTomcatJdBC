# Tomcat-JDBC lib cause problem with spring native
If the Tomcat-JDBC library is used in a spring native project, the compilation to a native image causes this error.

>   Exception in thread "main" org.springframework.boot.context.properties.bind.MissingParametersCompilerArgumentException: Constructor binding in a native image requires compilation with -parameters but the following classes were compiled without it:
>   org.apache.tomcat.jdbc.pool.PoolProperties$InterceptorProperty

# Steps to reproduce
1. run ./gradlew nativeCompile

# Solution
1. Build tomcat-jdbc lib with javac parameter **-paramters**
