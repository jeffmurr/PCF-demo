
PCF Demo
=========
1) Login to your org and space:
cf login -a api.my-unique-domain.io
When prompted please select username, password, org and space
2) Deploy application for the main directory:
cf push (name, hostname, instances, memory is specified in the manifest.yml)
You can use specific manifest for specific env. Use -f to specify specific manifest
Push the application initially with no service bound.
3) Marketplace Services: Notice it will alert no RabbitMQ service is bound.. the link "Stream Data" will not work either.
Now, go to marketplace select cloudamqp and bind a RabbitMQ service. Once bound, please restage the app to inject the environment variables.
Click "Stream Data" and see the fun start. Click on a state to detail orders going throw it.
4) Self Healing: Click "Kill App" and watch the application crashing.. it will show as "crashed" when you visualize events (cf events <app_name>). Health manager will automatically restart the app for you.
5) Scaling: You can manually scale the app by clicking the scale button on the apps dashbpard. You can also bind autoscaler from the marketplace services to automatically scale your apps on a schedule, cpu, http throughput, latency and so on.
6) A/B testing: Deploy version 1 and version 2 for the app. You can assign the same route of version 1 to v2 and scale up the # of instances to v2, you will see traffic now flowing to v2 as well for example 2 instances of v1 vs 3 instances for v2. You can also use PCF route services for additional configuration[https://docs.pivotal.io/pivotalcf/1-12/services/route-services.html#introduction].
7) Zero downtime app upgrades: Once satisfied with A/B testing or friends and family testing. You can now simple scale up version 2 of your app to your desired levels. Stop and delete version 1 of the app, hence achieving true zero downtime requirements.
8) Logging/Metrics: You can click on the PCF Metrics link and pick the application you want to see the related metrics and logs along with it. You can also click on trace explore to perform latency analysis on your apps.





