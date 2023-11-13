# MPI-Numeric
This repository contains how to execute a numeric program in python using MPI with an Ubuntu Master &amp; 3 Ubuntu Slave

# Things to Prepared
1. Ubuntu Desktop Master
2. 3 Ubuntu Desktop Slave
3. MPI (Master dan Slave)
4. SSH (Master dan Slave)
5. NFS (Master dan Slave)
6. Numeric Code

# Topology
![Topologi](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/2815c150-942f-4296-9ba2-86cf108ad343)

# Configure "etc/hosts/" File
1. Make sure the installed Ubuntu Desktop uses a Network Bridged Adapter, and each Master and Slave are connected to the same internet. Make sure the Master and Slave IPs are known
2. First of all, enter the command to make changes to the /etc/hosts file as shown in the image beside.
![PP2](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/a36c1bba-c702-4073-88e4-7465712e5122)
3. Then, configure etc/hosts in etc/hosts, as shown in the image below
![PP1](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/bd4a688c-fb00-416d-9972-e09af1d6b458)

# Make New User
1. On Ubuntu Master and Slave, you need to create a new user with the command
![PP3](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/94cebcd4-5406-4328-b865-d5521ee2dd2f)
Fill in all requests requested by the system, with the user name which must be the same on the Master and each Slave
2. Then in Master and Slave, enter the newly created user with the following command.
![PP4](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/1af57950-95c5-417e-bdec-30b7446f21b2)

# Configurate SSH
1. On Ubuntu Master and Slave, you need to install SSH yourself first with the following command.
![PP5](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/ed5daa69-03a3-4efc-892f-e2e3408c5c1b)

2. Once installed, you can check SSH with the following command.
![PP6](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/86f0191b-ef8a-415c-b7eb-a40e42470feb)

3. So the result after the SSH installation will be like the following image.
![PP26](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/6e60cebb-d8aa-42ca-8d46-bfa00491545d)

# Generate & Copy Keygen from Master to Slave
1. On Ubuntu Master, perform the following command
![PP7](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/8f127f0a-1566-4549-81e6-8051ef901975)
Later the system will ask for some input, just skip it. Later, there will be an .ssh folder containing the id_rsa and id_rsa.pub files

2. Then on Ubuntu Master, copy the contents of the id_rsa.pub file to the authorized_keys file with ssh as shown in the following image
![PP8](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/a4a5e610-2ffd-484d-991b-9800949ab755)
![PP9](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/16ea1ac9-fd38-4cf4-b44e-2a5c666b62a5). Copy and paste several times from Master to Slave by changing the host.

# Configure NFS
1. On Ubuntu Master and Slave, you need to create a directory with the following command.
![PP10](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/4c1f490f-2c10-479d-8db5-1485d34a0562)

2. Then on Ubuntu Master, install NFS Server with the following command.
![PP11](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/001572bb-23db-4240-87d4-695cb5a93de9)

3. Still on Ubuntu Master, open the /etc/exports file with nano, and add the line as below.
![PP12](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/1dab408e-f89a-4a64-9f44-0c72fe8f2c7a)
![PP13](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/cfd9af8f-4bac-4be4-a87d-d5cb5165ddd6)

4. After configuring the /etc/exports file, enter the following command.
![PP14](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/bbf836c9-0043-4823-8e10-925854c529d6)
![PP15](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/f4bbe1a3-f059-4fac-90ee-89c9671fc7b4)

5. Then on Ubuntu Slave, install the NFS Client with the following command.
![PP16](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/c7f78be1-aca5-4db7-b74a-65238f96124d)

6. Finally, mount 3 Ubuntu Slaves with the following command.
![PP17](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/fcfb1855-2bd0-4e71-910a-b5714bde6388)


# Numeric Program Execution
1. On Ubuntu Master and Server, perform the following commands for MPI installation.
![PP18](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/59f02175-3818-434c-a440-d804f7d458ba)

2. Then on Ubuntu Master, create a python file in the shared folder with the command below.
![PP27](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/2ea8d718-07ee-45f2-9171-bb51f7d43873)
![PP28](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/27889281-3a4f-4ec4-8c95-145960cdc89f)

3. Make sure you have already install numpy to execute the numeric program
![PP34](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/9fb47865-4e5c-465e-9f62-93b9d0ea8bbd)

4. Before executing the Numeric code, first carry out testing on MPI with the following command
![PP21](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/9f3ea032-895d-48a2-bbec-46965f3d4e82)
![PP22](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/6fab69f1-497a-4fb8-98e4-98722aba7bba)
![PP23](https://github.com/ShinnoHonobu/MPI-BubbleSort/assets/113822318/46710b3b-bb83-451b-af76-50a51a029c5e)

5. Enter the Numeric code in the python file with the command below.

    ![PP27](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/2ea8d718-07ee-45f2-9171-bb51f7d43873)
  
    You can check the code in the code menu

6. Next, run the file with the following command so that the following output appears.
- Run Without MPI

  ![PP29](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/3847a01b-677d-4c88-9875-6d4959fb89c2)
- Run With Master Only

  ![PP30](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/bd220613-2f1b-4b04-98c4-7878d2b7ddaf)
- Run With Master and Slave1

  ![PP31](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/5787fac2-fc24-438d-8980-46472ffd6274)
- Run With Master, Slave1, and Slave2

  ![PP32](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/762aeffe-f707-4380-8f60-566e45175d2e)
- Run With Master, Slave1, Slave2, Slave3

  ![PP33](https://github.com/ShinnoHonobu/MPI-Numeric/assets/113822318/930c55a2-7019-4719-a327-6c6382a73697)
