# Dockerfile Instructions

Dockerfile instructions are used to build and configure Docker images and containers.

## 1. FROM

**Description:** Chooses the starting image on which the Docker image will be built.

**Syntax:**

```dockerfile
FROM <image>:<tag>
```

**Example:**

```dockerfile
FROM python:3.12
```

---

## 2. RUN

**Description:** Executes a command while creating the Docker image. It is commonly used for installing software and dependencies.

**Syntax:**

```dockerfile
RUN <command>
```

**Example:**

```dockerfile
RUN apt-get update
```

---

## 3. CMD

**Description:** Defines the default command that Docker runs when the container is started. It can be replaced by a command given with `docker run`.

**Syntax:**

```dockerfile
CMD ["command", "argument"]
```

**Example:**

```dockerfile
CMD ["python", "app.py"]
```

---

## 4. COPY

**Description:** Transfers files or folders from the build context into the Docker image.

**Syntax:**

```dockerfile
COPY <source> <destination>
```

**Example:**

```dockerfile
COPY app.py /app/
```

---

## 5. ADD

**Description:** Adds files or directories to the image. It provides some additional features compared with `COPY`, such as extracting local compressed archives.

**Syntax:**

```dockerfile
ADD <source> <destination>
```

**Example:**

```dockerfile
ADD application.tar.gz /app/
```

---

## 6. LABEL

**Description:** Attaches descriptive information to a Docker image. Labels can be useful for identifying and managing images.

**Syntax:**

```dockerfile
LABEL <key>=<value>
```

**Example:**

```dockerfile
LABEL version="1.0"
```

---

## 7. EXPOSE

**Description:** Indicates the network port that an application inside the container is expected to use. It does not make the port accessible from the host automatically.

**Syntax:**

```dockerfile
EXPOSE <port>
```

**Example:**

```dockerfile
EXPOSE 8080
```

---

## 8. ENV

**Description:** Creates environment variables that can be accessed by processes running inside the container.

**Syntax:**

```dockerfile
ENV <key>=<value>
```

**Example:**

```dockerfile
ENV APP_MODE=production
```

---

## 9. ENTRYPOINT

**Description:** Defines the main program that the container is designed to execute. Arguments can be supplied through `CMD` or `docker run`.

**Syntax:**

```dockerfile
ENTRYPOINT ["command", "argument"]
```

**Example:**

```dockerfile
ENTRYPOINT ["java", "-jar", "app.jar"]
```

---

## 10. USER

**Description:** Specifies which user should be used to execute commands and applications inside the container.

**Syntax:**

```dockerfile
USER <username>
```

**Example:**

```dockerfile
USER appuser
```

---

## 11. WORKDIR

**Description:** Selects the default directory for following Dockerfile instructions and for the application when the container starts.

**Syntax:**

```dockerfile
WORKDIR <directory>
```

**Example:**

```dockerfile
WORKDIR /opt/application
```

---

## 12. ARG

**Description:** Creates a variable that can be supplied while building the Docker image. Unlike `ENV`, it is mainly intended for the image build stage.

**Syntax:**

```dockerfile
ARG <name>=<default-value>
```

**Example:**

```dockerfile
ARG APP_VERSION=2.0
```

---

## 13. ONBUILD

**Description:** Stores an instruction that will be triggered later when another Dockerfile uses this image as its base image.

**Syntax:**

```dockerfile
ONBUILD <instruction>
```

**Example:**

```dockerfile
ONBUILD COPY . /app
```
