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
3. Guarnteed:
   ========================================
   . Mention of CPU/Memory in yaml
   . Request=Limit
   . Highest priority pods.                
