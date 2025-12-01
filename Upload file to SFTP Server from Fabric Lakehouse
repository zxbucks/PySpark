import paramiko

# SFTP details
sftp_host = "Replace with your sftp connection"
sftp_port = 22
sftp_user = "Replace with your sftp connection"
sftp_pass = "Replace with your sftp connection"


file_to_upload = "/lakehouse/default/Files/Hello_World.csv"
remove_sftp_path = "/Hello_World.csv"

try:
    transport = paramiko.Transport((sftp_host, sftp_port))
    transport.connect(username=sftp_user, password=sftp_pass)
    sftp = paramiko.SFTPClient.from_transport(transport)

    #Upload a file
    sftp.put(file_to_upload, remove_sftp_path)
    print(f"✅ File uploaded to SFTP: {remove_sftp_path}")

    #List files
    files = sftp.listdir("/")
    print("Files and directories:", files)


    sftp.close()
    transport.close()
except Exception as e:
    print(f"❌ SFTP upload failed: {e}")

