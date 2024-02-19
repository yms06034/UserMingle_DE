**UserMingle : Kafka-Driven User Profile Streaming**

본 프로젝트는 Random User Generator API를 사용하여 Airflow DAG Pipeline를 사용하여 데이터를 간헐적으로 가져와 Postgres DB에 저장했습니다.
전체 스트르밍 프로세스는 Zookeeper Pipeline을 가진 Kafka 설정에 의해 관리 되고, 마지막으로 Spark에서 스트림 데이터를 가져와 Cassandra DB로 저장됩니다.
해당 프로젝트는 Docker 컨테이너화로 진행하였습니다.

**Solution Architecture**

![image](https://github.com/vedanthv/data-engineering-portfolio/assets/44313631/bf025b1f-e051-4f1e-9353-1d2b837060b4)

**Tech Stack**

- **Apache Airflow**: 파이프라인 조정 및 가져온 데이터를 PostgreSQL 데이터베이스에 저장하는 역할.
- **Apache Kafka and Zookeeper**: PostgreSQL에서 프로세싱 엔진으로 데이터를 스트리밍하는 데 사용됩니다.
- **Control Center and Schema Registry**: Kafka 스트림의 모니터링 및 Schema 관리 지원.
- **Apache Spark**: 마스터 노드 및 작업자 노드를 사용한 데이터 처리용.
- **Cassandra**: 처리된 데이터가 저장.


**Demo**

**Apache Airflow DAG**

![image](https://github.com/vedanthv/data-engineering-portfolio/assets/44313631/3f34b376-804b-4534-a2c6-0225049350c0)

**Confluent Control Center Consumption Stats and Health of Broker**

![image](https://github.com/vedanthv/data-engineering-portfolio/assets/44313631/0bc1fda0-8fd6-43cb-96e3-648f84fba894)

**Confluent Control Center Message Queue**

![image](https://github.com/vedanthv/data-engineering-portfolio/assets/44313631/ed4c9f80-0248-4502-b5c2-ddbd43ea7d81)
