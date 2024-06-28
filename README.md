first Add security rules[inbound rules one is ssh and another is nfs] 
TRY TO HOST DIFFERENT MACHINES OR INSTANCE[EXAMPLE-AWS,RED HAT, UBUNTU] IN DIFFERENT ZONE
one instance in southeast 1a IN AWS
second instance IN southeast1c using redhat
now add security group to each zone
Add rule -NFS 0000/0 
now search efs and create file system then go to networking and add security rules of 1a,1b,1c


***Commands run on aws instance**
sudo su -
 yum install nfs-utils -y
cat /etc/os-release
 rpmquery nfs-utils
mkdir efs

now go to efs of your instance select file system and select attach,now u will see the mount via dns..copy the mount point[using the nfs client] and paste on your terminal[remove / before efs because i have created same name directory named as efs]

cd /root/efs
touch prt.txt{1...100}
ll
now u will see ur text files

****Commands run on red hat instance****
run same command as aws
mkdir efs
cd /root/efs
ll
U will see the files that u have attcahed in previous zone


