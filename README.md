# DOCKER_PROCESSAMENTO-LOGS-E-REDES
Breve resumo sobre pontos importante no estudo de DOCKER sobre Processamento, Logs e redes
## ⚡ Processamento no Docker
### Como Docker gerencia CPU e RAM dos containers?
- Containers **compartilham recursos** do host, mas é possível **limitar** CPU e memória.
- **Monitorar consumo** do container em tempo real:
  ```bash
  docker stats
  ```
- **Limitar CPU e RAM de um container:**
  ```bash
  docker run -d --memory="512m" --cpus="1.5" nginx
  ```
  *→ Define máximo de 512MB de RAM e 1.5 núcleos de CPU para o container.*

---

## 📜 Logs no Docker
### Onde ficam os logs dos containers?
- Para ver os logs de um container específico:
  ```bash
  docker logs nome_do_container
  ```
- Para acompanhar logs em tempo real (**modo live**):
  ```bash
  docker logs -f nome_do_container
  ```
- Para salvar logs em um arquivo:
  ```bash
  docker logs nome_do_container > logs.txt
  ```

---

## 🌐 Rede no Docker
### Tipos de redes no Docker
- **bridge** → Padrão, isola containers da rede do host.
- **host** → Usa diretamente a rede do host.
- **none** → Sem rede (modo isolado).
- **custom networks** → Para comunicação entre múltiplos containers.

🔗 **Listar redes disponíveis:**
```bash
docker network ls
```

🌍 **Criar uma rede personalizada:**
```bash
docker network create minha_rede
```

🔗 **Rodar um container dentro dessa rede:**
```bash
docker run -d --network=minha_rede --name meu_container nginx
```

---

## 🛠 Resumo Final
- 🖥 **Processamento** → Controle CPU/RAM com `docker stats` e flags `--memory` / `--cpus`.
- 📜 **Logs** → Use `docker logs -f nome_do_container` para acompanhar em tempo real.
- 🌍 **Rede** → Containers podem ser isolados ou conectados por redes personalizadas.
