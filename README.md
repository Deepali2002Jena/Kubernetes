# Kubernetes
Kubernetes access though the remote version control

                                     QUALITY OF SERVICE
                            ========================================================
1. Best effort:
   ================================
   . There is no mention of cpu/memory in yaml
   . Kubernetes will try to give it  but number is committed.
   . These are the least priority pods.
2. Burstable:
   ==================================
   . Mention of cpu/memory in yaml
   . Request is guarnteed
   . Request is used by the scheduler for scheduling
   . Request is give and startup
   . Limit is the maximum, that the pod can use
   . This is the second priority pod
3. Guaranteed:
   ========================================
   . Mention of CPU/Memory in yaml
   . Request=Limit
   . Highest priority pods.
                   
                                                           PROBES
                           ======================================================================

   
1. Startup probe:
   =========================================
   . Startup probe will check the index.html file is there or not . If it is there and the pod is ready to take traffic it will be closed.
   . It will run only once and it will no longer executed.
   
3. Readiness probe:
   =========================================
   . Readiness probe will check the pod during the life of the pod.
   . It will start once the startup probe will end.
   . If two subsequent failuers are there, then the readiness probe will consider the pod is down and will quarantine the pod.
   . It will remove the pod from the service endpoint but it will keep checking the pods.
Main job: -To remove the bad pod in the service endpoiny and it will not give any bad experience to the user.

4. Liveness probe:
   ==========================================
   . To overcome from the readiness probe we will use liveness probe.
   . Failuer threshold of liveness probe will be slightly greater than the readiness probe.
   . If three subsequent failuer are there, then it will restart the container because images are readonly. If there is any issue with the process it will restart and issue will be resolved.
   
