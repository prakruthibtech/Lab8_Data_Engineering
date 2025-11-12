project:
  name: Hospital Patient Records Cleaning & Automation
  author: Prakruthi S
  university: R V University, Bangalore
  degree: B.Tech in Computer Science and Engineering
  description: >
    A Snowflake-based ETL project that automates the cleaning of hospital patient records
    using Streams and Tasks for real-time, structured, and analytics-ready data.
  tags:
    - Snowflake
    - ETL
    - Data Cleaning
    - Automation
    - SQL
    - Healthcare

implementation:
  database:
    name: HOSPITAL_DB
    schema: PATIENT_SCHEMA
  tables:
    raw_table: RAW_PATIENTS
    clean_table: CLEAN_PATIENTS
  stream:
    name: RAW_PATIENTS_STREAM
    type: Change Data Stream
    purpose: Tracks inserts and updates for incremental cleaning
  task:
    name: PATIENT_CLEANING_TASK
    schedule: "*/10 * * * * UTC"
    warehouse: MY_TASK_WAREHOUSE
    function: Cleans and transforms raw patient data automatically
  sample_data:
    - patient_id: "1"
      name: "John Doe"
      age: "30"
      gender: "Male"
      visit_date: "2025-10-21"
      diagnosis_code: "D01"
      bill_amount: "5,000"
    - patient_id: "2"
      name: "Jane Smith"
      age: "Twenty-Five"
      gender: "Female"
      visit_date: "21-10-2025"
      diagnosis_code: "D02"
      bill_amount: "3,200"

automation:
  process:
    - Create database and schema
    - Create raw and clean tables
    - Create stream on raw table
    - Insert messy data
    - Schedule and execute cleaning task
    - Verify clean dataset
  verification_query: "SELECT * FROM CLEAN_PATIENTS ORDER BY patient_id;"

extension:
  missing_diagnosis_table: PATIENTS_MISSING_DIAGNOSIS
  purpose: Flags records with missing diagnosis_code

outcome:
  summary: >
    Automated ETL pipeline built in Snowflake to maintain accurate, cleaned,
    and real-time hospital patient data.
  benefits:
    - Real-time updates
    - Reduced manual intervention
    - Improved data accuracy and auditability
