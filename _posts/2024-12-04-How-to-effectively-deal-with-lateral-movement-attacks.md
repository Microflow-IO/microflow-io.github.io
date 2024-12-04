# How to effectively deal with lateral movement attacks?

**Leo Young, 12/04/2024** 

Undoubtedly, lateral movement attacks are the most prevalent attack methods in production environments, yet the current methods all have significant flaws.

- **EDR/HIDS:**  They belong to the principle of host-level security baseline detection and are not targeted at lateral attacks on various networks and applications;
- **Log analysis/SOC:**  The real-time performance is insufficient, coupled with a lack of network logs, and business logs are often severely heterogeneous and incomplete;
- **API security gateway:**  The biggest drawback is that its deployment location determines that it has many detection blind spots, making it unable to form comprehensive detection capabilities;

So, how does Nano achieve high-quality detection of the risk of lateral movement attacks?

The principle is straightforward. As illustrated in the figure below, we will discover this simple yet highly effective approach that can effectively counteract most horizontal movement attacks. Furthermore, the entire approach truly achieves non-intrusive, no blind spots, global coverage, real-time performance, and possesses traceability and analysis capabilities. It represents a scene innovation with immense commercial value.

```mermaid
graph TB  
    subgraph "Cloud and Cloud-Native"  
        VM1["Virtual Machine 1 (with Nano)"]  
        VM2["Virtual Machine 2 (with Nano)"]  
        Node1["Node 1 (with Nano Pod)"]  
        Node2["Node 2 (with Nano Pod)"]  
    end  

    Middleware["Logstash/Fluentd"]  
    MSA["ModSecurity for Anylog + STIX Spark"]  
    AnalyticsPlatform["SOC/XDR/Log Analytics"]  

    VM1 -.->|"JSON over UDP"| Middleware  
    VM2 -.->|"JSON over UDP"| Middleware  
    Node1 -.->|"JSON over UDP"| Middleware  
    Node2 -.->|"JSON over UDP"| Middleware  

    Middleware -.->|"JSON Data"| AnalyticsPlatform  
    Middleware -.->|"JSON Data"| MSA  

    MSA -.->|"Alerts (Syslog)"| AnalyticsPlatform  

    classDef vm fill:#e1f5fe,stroke:#01579b,stroke-width:2px;  
    classDef node fill:#e8f5e9,stroke:#1b5e20,stroke-width:2px;  
    classDef middleware fill:#fff3e0,stroke:#e65100,stroke-width:2px;  
    classDef msa fill:#fce4ec,stroke:#880e4f,stroke-width:2px;  
    classDef analytics fill:#f3e5f5,stroke:#4a148c,stroke-width:2px;  

    class VM1,VM2 vm;  
    class Node1,Node2 node;  
    class Middleware middleware;  
    class MSA msa;  
    class AnalyticsPlatform analytics;
```

------

**microflow.io**

leoyoung@microflow.io
