## 🐳 CMD vs ENTRYPOINT in Docker

When writing a Dockerfile, both `CMD` and `ENTRYPOINT` 
define what runs when the container starts. However, they serve different purposes and behave differently.

---

### 🔹 CMD (Default Command)

- **Purpose:** Sets default arguments for the container's main process.
- **Overridable:** ✅ Yes – can be overridden by arguments passed to `docker run`.
- **Syntax Options:**
  - Shell form: `CMD echo "Hello World"`
  - Exec form: `CMD ["echo", "Hello World"]`

---

### 🔷 ENTRYPOINT (Fixed Command)

- **Purpose:** Specifies the container's main executable.
- **Overridable:** ❌ No – unless you use the `--entrypoint` flag with `docker run`.
- **Syntax:** Recommended in exec form: `ENTRYPOINT ["executable", "param1"]`

---

### 🔁 Combining ENTRYPOINT and CMD

You can use both for more flexibility:

```dockerfile
ENTRYPOINT ["python3", "app.py"]
CMD ["--port", "8080"]

------------------------------

