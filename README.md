# CMSC126_Activity_Unit5_Unit6




```mermaid
flowchart TD
    Student[🎓 Student Browser]
    Student --> CF

    subgraph Edge["Edge Layer"]
        CF[Cloudflare\nDDoS protection · HTTPS · Caching]
    end

    subgraph UP["UP Server"]
        Nginx[Nginx\nReverse Proxy · Routes Traffic]
        LB[Load Balancer\nDistributes across app instances]
        Nginx --> LB
    end

    subgraph AppLayer["App Layer (Docker Containers)"]
        N1[Next.js Instance 1]
        N2[Next.js Instance 2]
    end

    subgraph DataLayer["Data Layer (Docker Containers)"]
        Redis[Redis Cache\nFrequently accessed data]
        PG[PostgreSQL DB\nPrimary database]
    end

    subgraph Backup["Backup & Scale"]
        AB[Automated Backups\nDaily snapshots to secure storage]
        GCP[GCP Singapore\nAuto-scales VMs during peak enrollment\nShuts down when traffic drops]
    end

    CF --> Nginx
    LB --> N1
    LB --> N2
    N1 --> Redis
    N2 --> Redis
    Redis --> PG
    PG --> AB
    PG --> GCP
```
## Mock-ups

1. **Homepage**
   ![Home page](https://github.com/grape-ss/CMSC126_Activity_Unit5_Unit6/blob/78abdaaa1e069dddacded08bc52b7a453011e05f/Landing_Home.png)
3. **Student Dashboard**
   ![image alt]()
5. **View Schedule**
   - **Tabular View**
      ![image alt]()
   - **List View**
      ![image alt]()
6. **Grades**
   ![image alt]()
