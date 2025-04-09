[cybersecurityrtms-aefa] Details
============================

Generated On: 2025-04-09 17:06:10 UTC

TML Solution DAG Parameters' Details: User Chosen Parametets
----------------------------

STEP 1: Get TML Core Params: `tml_system_step_1_getparams_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_1_getparams_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - solutionname
     - cybersecurityrtms-aefa
   * - solutiontitle
     - Entity-Based Real-Time Advanced Cybersecurity Prevention and Monitoring
   * - solutiondescription
     - TML Real-Time Memory of Sliding Time Windows For Advanced Cybersecurity Prevention
   * - brokerhost
     - 127.0.0.1
   * - brokerport
     - 9092
   * - cloudusername
     - None
   * - ingestdatamethod
     - LOCALFILE
 
STEP 2: Create Kafka Topics: `tml_system_step_2_kafka_createtopic_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_2_kafka_createtopic_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - companyname
     - Otics
   * - myname
     - Sebastian
   * - myemail
     - Sebastian.Maurice
   * - mylocation
     - Toronto
   * - replication
     - 1
   * - numpartitions
     - 1
   * - enabletls
     - 1
   * - microserviceid
     - 
   * - raw_data_topic
     - iot-raw-data,rtms-stream-mylogs,rtms-stream-mylogs2
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - ml_data_topic
     - ml-data
   * - prediction_data_topic
     - prediction-data

STEP 3: `Produce to Kafka Topics <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_read_LOCALFILE_step_3_kafka_producetotopic_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PRODUCETYPE
     - LOCALFILE
   * - inputfile
     - /rawdatademo/cisco_network_data.txt
   * - TOPIC
     - iot-raw-data
   * - PORT
     - _5050
   * - IDENTIFIER
     - TML solution,/rawdatademo/cisco_network_data.txt
   * - HTTPADDR
     - https://
   * - FROMHOST
     - ('seb', '127.0.1.1')
   * - TOHOST
     - 0.0.0.0
   * - CLIENTPORT
     - Not Applicable
   * - TSS_CLIENTPORT
     - Not Applicable
   * - TML_CLIENTPORT
     - Not Applicable
   * - docfolder
     - mylogs,mylogs2
   * - doctopic
     - rtms-stream-mylogs
   * - chunks
     - 3000
   * - docingestinterval
     - 30

STEP 4: Preprocesing Data: `tml-system-step-4-kafka-preprocess-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - iot-raw-data,rtms-stream-mylogs,rtms-stream-mylogs2
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - preprocessconditions
     - 
   * - delay
     - 70
   * - maxrows
     - 800
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 1
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - preprocesstypes
     - anomprob,trend,avg
   * - pathtotmlattrs
     - --pathtotmlattrs--
   * - identifier
     - RTMS Cybersecurity Prevention
   * - jsoncriteria
     - uid=hostName,filter:allrecords~subtopics=hostName,hostName,hostName~values=inboundpackets,outboundpackets,pingStatus~identifiers=inboundpackets,outboundpackets,pingStatus~datetime=lastUpdated~msgid=~latlong=

STEP 4a: Preprocesing Data: `tml-system-step-4a-kafka-preprocess-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4a_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic1--
   * - preprocess_data_topic
     - --preprocess_data_topic1--
   * - preprocessconditions
     - --preprocessconditions1--
   * - delay
     - --delay1--
   * - maxrows
     - --maxrows1--
   * - array
     - --array1--
   * - saveasarray
     - --saveasarray1--
   * - topicid
     - --topicid1--
   * - rawdataoutput
     - --rawdataoutput1--
   * - asynctimeout
     - --asynctimeout1--
   * - timedelay
     - --timedelay1--
   * - preprocesstypes
     - --preprocesstypes1--
   * - pathtotmlattrs
     - --pathtotmlattrs1--
   * - identifier
     - --identifier1--
   * - jsoncriteria
     - --jsoncriteria1--

STEP 4b: Preprocesing Data: `tml-system-step-4b-kafka-preprocess-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4b_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - --raw_data_topic2--
   * - preprocess_data_topic
     - --preprocess_data_topic2--
   * - preprocessconditions
     - --preprocessconditions2--
   * - delay
     - --delay2--
   * - maxrows
     - --maxrows2--
   * - array
     - --array2--
   * - saveasarray
     - --saveasarray2--
   * - topicid
     - --topicid2--
   * - rawdataoutput
     - --rawdataoutput2--
   * - asynctimeout
     - --asynctimeout2--
   * - timedelay
     - --timedelay2--
   * - preprocesstypes
     - --preprocesstypes2--
   * - pathtotmlattrs
     - --pathtotmlattrs2--
   * - identifier
     - --identifier2--
   * - jsoncriteria
     - --jsoncriteria2--

STEP 4c: Preprocesing Data: `tml-system-step-4c-kafka-preprocess-dag  <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_4c_kafka_preprocess_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - raw_data_topic
     - iot-preprocess
   * - preprocess_data_topic
     - rtms-preprocess
   * - delay
     - 70
   * - maxrows
     - 100
   * - array
     - 0
   * - saveasarray
     - 1
   * - topicid
     - -999
   * - rawdataoutput
     - 1
   * - asynctimeout
     - 120
   * - timedelay
     - 0
   * - searchterms
     - rgx:p([a-z]+)ch ~~~ |authentication failure,--entity-- password failure
   * - rtmsstream
     - rtms-stream-mylogs
   * - identifier
     - RTMS Past Memory of Events
   * - rememberpastwindows
     - 500
   * - patternwindowthreshold
     - 30
   * - localsearchtermfolder
     - |mysearchfile1,|mysearchfile2
   * - localsearchtermfolderinterval
     - 0
   * - rtmsscorethreshold
     - 0.6
   * - rtmsscorethresholdtopic
     - rtmstopic
   * - attackscorethreshold
     - 0.6
   * - attackscorethresholdtopic
     - attacktopic
   * - patternscorethreshold
     - 0.6
   * - patternscorethresholdtopic
     - patterntopic
   * - rtmsfoldername
     - rtms2
   * - rtmsmaxwindows
     - 1000000
   * - RTMS Output Github Link
     - `Output Data URL <https:\/\/github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/rtms2>`_

STEP 5: Entity Based Machine Learning : `tml-system-step-5-kafka-machine-learning-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_5_kafka_machine_learning_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - ml_data_topic
     - ml-data
   * - modelruns
     - --modelruns--
   * - offset
     - -1
   * - islogistic
     - --islogistic--
   * - networktimeout
     - --networktimeout--
   * - modelsearchtuner
     - --modelsearchtuner--
   * - processlogic
     - --processlogic--
   * - dependentvariable
     - --dependentvariable--
   * - independentvariables
     - --independentvariables--
   * - rollbackoffsets
     - --rollbackoffsets--
   * - topicid
     - -999
   * - consumefrom
     - --consumefrom--
   * - fullpathtotrainingdata
     - --fullpathtotrainingdata--
   * - transformtype
     - --transformtype--
   * - sendcoefto
     - --sendcoefto--
   * - coeftoprocess
     - --coeftoprocess--
   * - coefsubtopicnames
     - --coefsubtopicnames--
   * - ML Output Github Link
     - `Output Data URL <--mloutputurl-->`_

STEP 6: Entity Based Predictions: `tml-system-step-6-kafka-predictions-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_6_kafka_predictions_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - preprocess_data_topic
     - iot-preprocess,iot-preprocess2,rtms-preprocess,attacktopic,rtmstopic,patterntopic
   * - ml_prediction_topic
     - --ml_prediction_topic--
   * - streamstojoin
     - --streamstojoin--
   * - inputdata
     - --inputdata--
   * - consumefrom
     - --consumefrom2--
   * - offset
     - -1
   * - delay
     - 70
   * - usedeploy
     - --usedeploy--
   * - networktimeout
     - --networktimeout--
   * - maxrows
     - 800
   * - topicid
     - -999
   * - pathtoalgos
     - --pathtoalgos--

STEP 7: Real-Time Visualization: `tml-system-step-7-kafka-visualization-dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_7_kafka_visualization_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^

.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - vipervizport
     - 49689
   * - topic
     - rtms-preprocess
   * - dashboardhtml
     - dashboard-rtms.html
   * - secure
     - 1
   * - offset
     - -1
   * - append
     - 0
   * - chip
     - amd64
   * - rollbackoffset
     - 400

STEP 8: `tml_system_step_8_deploy_solution_to_docker_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_8_deploy_solution_to_docker_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Docker Container
     - /cybersecurityrtms-aefa-amd64 (https://hub.docker.com/r//cybersecurityrtms-aefa-amd64)
   * - Docker Run Command
     - docker run -d --net=host -p 5050:5050 -p 4040:4040 -p 6060:6060 \
          --env TSS=0 \
          --env SOLUTIONNAME=cybersecurityrtms-aefa \
          --env SOLUTIONDAG=solution_preprocessing_dag-cybersecurityrtms-aefa \
          --env GITUSERNAME=<Enter Github Username> \
          --env GITPASSWORD='<Enter Github Password>' \          
          --env GITREPOURL=<Enter Github Repo URL> \
          --env SOLUTIONEXTERNALPORT=5050 \
          -v /var/run/docker.sock:/var/run/docker.sock:z \
          -v /your_localmachine/foldername:/rawdata:z \
          --env CHIP=amd64 \
          --env SOLUTIONAIRFLOWPORT=4040 \
          --env SOLUTIONVIPERVIZPORT=6060 \
          --env DOCKERUSERNAME='' \
          --env EXTERNALPORT=39399 \
          --env KAFKABROKERHOST=127.0.0.1:9092 \                    
          --env KAFKACLOUDUSERNAME='<Enter API key>' \
          --env KAFKACLOUDPASSWORD='<Enter API secret>' \          
          --env SASLMECHANISM=PLAIN \                    
          --env VIPERVIZPORT=49689 \
          --env MQTTUSERNAME='' \
          --env MQTTPASSWORD='' \          
          --env AIRFLOWPORT=9000 \
          --env READTHEDOCS='<Enter Readthedocs token>' \
          --env step4cmaxrows="100" \ 
          --env step4crawdatatopic="iot-preprocess" \ 
          --env step4csearchterms="rgx:p([a-z]+)ch ~~~ |authentication failure,--entity-- password failure" \ 
          --env step4crememberpastwindows="500" \ 
          --env step4cpatternwindowthreshold="30" \ 
          --env step4crtmsscorethreshold="0.6" \ 
          --env step4cattackscorethreshold="0.6" \ 
          --env step4cpatternscorethreshold="0.6" \ 
          --env step4crtmsstream="rtms-stream-mylogs" \ 
          --env step4clocalsearchtermfolder="|mysearchfile1,|mysearchfile2" \ 
          --env step4clocalsearchtermfolderinterval="60" \ 
          --env step4crtmsfoldername="rtms2" \ 
          --env step3localfiledocfolder="mylogs,mylogs2" \ 
          --env step4crtmsmaxwindows="1000000" \ 
          --env step9pgptcontainername="maadsdocker/tml-privategpt-with-gpu-nvidia-amd64-v2" \ 
          --env step9contextwindow="8192" \ 
          --env step9vectordimension="768" \ 
          --env step9temperature="0.1" \ 
          --env step4raw_data_topic="iot-raw-data" \ 
          --env step4preprocesstypes="anomprob,trend,avg" \ 
          --env step4jsoncriteria="uid=hostName,filter:allrecords~subtopics=hostName,hostName,hostName~values=inboundpackets,outboundpackets,pingStatus~identifiers=inboundpackets,outboundpackets,pingStatus~datetime=lastUpdated~msgid=~latlong=" \ 
          --env step4preprocess_data_topic="iot-preprocess" \ 
          --env step4ajsoncriteria="uid=tactic,filter:allrecords~subtopics=technique,technique,technique~values=FinalAttackScore,FinalPatternScore,RTMSSCORE~identifiers=FinalAttackScore,FinalPatternScore,RTMSSCORE~datetime=TimeStamp~msgid=kafkakey~latlong=" \ 
          --env step4amaxrows="50" \ 
          --env step4apreprocesstypes="avg" \ 
          --env step4araw_data_topic="rtms-pgpt-ai" \ 
          --env step4apreprocess_data_topic="rtms-pgpt-ai-mitre" \  
          /cybersecurityrtms-aefa-amd64

STEP 9: `tml_system_step_9_privategpt_qdrant_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_9_privategpt_qdrant_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - PrivateGPT Container
     - --pgptcontainername--
   * - PrivateGPT Run Command
     - --privategptrun--
   * - Qdrant Container
     - --qdrantcontainer--
   * - Qdrant Run Command
     - --qdrantrun--
   * - Consumefrom
     - --consumefrom--
   * - pgpt_data_topic
     - --pgpt_data_topic--
   * - offset
     - -1
   * - rollbackoffset
     - 400
   * - topicid
     - -999
   * - enabletls
     - 1
   * - partition
     - --partition--
   * - prompt
     - --prompt--
   * - context
     - --context--
   * - jsonkeytogather
     - --jsonkeytogather--
   * - keyattribute
     - --keyattribute--
   * - keyprocesstype
     - --keyprocesstype--
   * - vectordbcollectionname
     - --vectordbcollectionname--
   * - concurrency
     - --concurrency--
   * - CUDA_VISIBLE_DEVICES
     - --cuda--
   * - pgpthost
     - --pgpthost--
   * - pgptport
     - --pgptport--
   * - hyperbatch
     - --hyperbatch--
   * - docfolder
     - --docfolder--
   * - docfolderingestinterval
     - --docfolderingestinterval--
   * - useidentifierinprompt
     - --useidentifierinprompt--
   * - searchterms
     - --searchterms--
   * - streamall
     - --streamall--
   * - temperature
     - --temperature--
   * - vectorsearchtype
     - --vectorsearchtype--
   * - llm
     - --llmmodel--
   * - embedding
     - --embedding--
   * - vectorsize
     - --vectorsize--
   * - contextwindowsize
     - --contextwindowsize--
   * - vectordimension
     - --vectordimension--
   * - mitrejson
     - --mitrejson--

STEP 10: `tml_system_step_10_documentation_dag <https://github.com/tsstmldemo/tsstmldemo/tree/main/tml-airflow/dags/tml-solutions/cybersecurityrtms-aefa/tml_system_step_10_documentation_dag-cybersecurityrtms-aefa.py>`_
^^^^^^^^^^^^^^^^^^^^^
.. list-table::

   * - **User Parameter**
     - **Chosen Value**
   * - Solution Documentation URL
     - https://cybersecurityrtms-aefa.readthedocs.io
