# Docker Boilerplate
## php8.2 xdebug3.4 symfony7.2 mongodb4.4 nginx

---

### Steps to setup

1. Clone the repository and enter the folder:
   ```bash
   git clone https://github.com/Yaradovhan/docker_boilerplate.git .
   ```  
2. Copy .env.example and/or update data:
   ```bash
   cp.env.example .env
   ```  
   
3. Build and start Docker containers:
   ```bash
   docker-compose up -d --build
   ```  

4. Create the `application` folder if not exist and enter it:
   ```bash
   mkdir application && cd application
   ```  

5. Clone the Symfony project:
   ```bash
   git clone https://github.com/Yaradovhan/symf_cryp_cur.git .
   ```  
   
6. Init Symfony project:
   ```bash
   docker compose exec app composer install
   ```

7. Open `http://localhost` in your browser to verify the project is installed correctly.
