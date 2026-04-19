Kubernetes Dashboard Admin Access

This repository contains configuration files to set up an admin user for the Kubernetes Dashboard. The files define a ServiceAccount and a ClusterRoleBinding that grant cluster-admin privileges to the dashboard user.

📄 Files

ServiceAccount: Creates an account named admin-user in the kubernetes-dashboard namespace.

ClusterRoleBinding: Binds the admin-user ServiceAccount to the cluster-admin role, granting full administrative rights.

⚙️ Usage

Apply the configuration:

kubectl apply -f dashboard-admin.yaml

Verify the ServiceAccount:

kubectl get serviceaccount admin-user -n kubernetes-dashboard

Verify the ClusterRoleBinding:

kubectl get clusterrolebinding admin-user-binding

🔑 Access Token

To log in to the Kubernetes Dashboard with the admin user:

Retrieve the token:

kubectl -n kubernetes-dashboard create token admin-user

Copy the token and paste it into the Dashboard login screen.

⚠️ Security Note

Granting cluster-admin rights gives full control over the cluster. Use this configuration only in trusted environments or for testing purposes. For production, consider creating more restrictive roles.

✅ Summary
This setup provides a quick way to access the Kubernetes Dashboard with full administrative privileges using a ServiceAccount and ClusterRoleBinding.
