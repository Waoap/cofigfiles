# 请将该 Dockerfile 放在后端项目的根目录下
FROM eclipse-temurin:21-jre-alpine
LABEL authors="Lyana-nullptr"\
  description="基于 JDK 21 构建的用于运行 Spring Boot 后端项目的镜像"

# 环境变量
ARG ARTIFACT_PATH=""
ENV ENV_ARTIFACT_PATH=${ARTIFACT_PATH}
ENV SERVER_PORT=8080

# 工作目录
WORKDIR /app

# 复制 .jar 文件
COPY ${ENV_ARTIFACT_PATH} /tmp
RUN if [ -d "/tmp" ]; then mv /tmp/*.jar app.jar; fi

# 启动参数
EXPOSE ${SERVER_PORT}

ENTRYPOINT ["java", "-jar", "app.jar"]
