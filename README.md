# kubectl-wrapper-IntelliJ-K8s-Plugin
A kubectl wrapper to fix IntelliJ K8s-Plugin Shortcomings

 I wrestled with the issue of accessing microk8s and gke via the IntelliJ K8s plugin.
I found that the plugin only has one server definition for defining a path the kubectl.
This does not work when you want to use microk8s and gke at the same time as microk8s seems to need to use microk8s.kubectl. 
Additionally, I found that kubectl was not able to find the “gke-gclound-auth” plugin when kubectl was referenced in the plugin.
The solutions to these issues was to create a wrapper script that would reference the correct version of kubectl depending on the 
“–context ” passed to the kubectl command. The scrip also adds the bin path to the gcloud installation so that the “gke-gclound-auth” 
plugin can be found by kubectl.

 I’m sure that I am not the only one to have experience these issues, so I am sharing the script…
I place the script into my home ~/bin/ directory and point to it in the K8s plugin “Server Settings”.
