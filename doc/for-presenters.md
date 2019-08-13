# For Presenters

This workshop is designed to show data engineers and system administrators how to architect a data infrastructure service using the Open Data Hub. Our goal is for engineers who are interested in developing platforms for the ML and Analytics needs to walk away having learned the following:

* How to deploy the Open Data Hub on an OpenShift cluster
* How to perform some data wrangling using Spark and Jupyter Notebooks in a hybrid cloud environment
* How to send data with Kafka, and monitor the health of their ODH environment with Prometheus and Grafana

## Background and workshop flow

Reading the [Open Data Hub reference architecture](https://opendatahub.io/arch.html) will provide a good starting point for understanding how the operator works as well as the individual components. The workshop can be broken into 3 main components, namely:

1. Deployment of ODH
2. Data wrangling in Hybrid Cloud with Spark and JupyterHub
3. Writing to Kafka and Monitoring

If you haven't used Jupyter notebooks before, please refer to the user documentation at [Project Jupyter](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#notebook-user-interface) to get comfortable with explaining details of how things work to workshop attendees. Some things to keep in mind, though, are:

* Jupyter notebooks are a literate programming environment combining cells containing narration and cells containing code. When a user executes a code cell, the output of running the code (whether a value, a table of records, a graph, or an error) is appended to the code cell.
* Shift+Enter always executes the current cell and advances to the next one. This is really all of the Jupyter interface anyone absolutely needs to know.
* Cells only run if you execute them, you can run a cell more than once, you can edit a cell and run it again (or not). This can be confusing! Don't assume that you can reproduce the output in a notebook you've seen
* If you get really stuck, head up to the Kernel menu and select Restart and clear output to start fresh.

## Modularity and extending the workshop

If there is more interest in the data-flow aspects of it, a possible improvement to the Kafka segment is utilizing the kafka-s3 connector to write to Ceph from a Jupyter notebook via Kafka.
Another interesting thing to do would be to demonstrate how to deploy a new application with Prometheus monitoring included.

## Workshop Steps

1. Attendees will first need to login to the RHPDS Cluster with provided user-credentials.
2. To deploy the ODH, users need to enter their project (it will have the same name as their username) followed by going to Catalog -> Installed Operators -> Open Data Hub Operator -> Open Data Hub -> Create Open Data Hub. The Custom Resource  should be left as is.
3. Once pods for all the applications are up, the attendees should go to Jupyterhub. They can find the url for their jupyterhub instance under networking -> routes. Jupyterhub is protected by oauth -- users will use the same credentials that they used to log into OpenShift.
4. It is at this point that they will import the hybrid-data-engineering notebook found under source/Notebooks.
5. Once they have finished the notebok, attendees should import and run the Kafka Consumer and Producer notebooks.
6. While these notebooks are running, attendees should go to Grafana (as a reminder, they can find the url under networking/routes).
7. We will then walk them through a step-by-step process for creating a dashboard for monitoring Kafka. The final dashboard (along with the required queries) can be found at source/Kafka.json.
