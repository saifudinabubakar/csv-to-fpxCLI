import csv

def csv_to_cli(csv_file):
    cli_commands = []
    with open(csv_file, 'r') as file:
        reader = csv.reader(file)
        headers = next(reader)
        for row in reader:
            policy = {}
            for i, header in enumerate(headers):
                policy[header] = row[i]
            cli_command = "config firewall policy\n"
            cli_command += "    edit {}\n".format(policy['Policy ID'])
            cli_command += "        set type {}\n".format(policy['Type'])
            cli_command += "        set name {}\n".format(policy['Name'])
            cli_command += "        set dstintf {}\n".format(policy['Destination Interface'])
            cli_command += "        set srcaddr {}\n".format(policy['Source Address'])
            cli_command += "        set dstaddr {}\n".format(policy['Destination Address'])
            cli_command += "        set action {}\n".format(policy['Action'])
            cli_command += "        set schedule {}\n".format(policy['Schedule'])
            cli_command += "        set explicit-web-proxy {}\n".format(policy['Explicit Web Proxy'])
            cli_command += "        set utm-status {}\n".format(policy['UTM Status'])
            cli_command += "        set webproxy-profile {}\n".format(policy['Webproxy-profile'])
            cli_command += "        set logtraffic {}\n".format(policy['Log Traffic'])
            cli_command += "        set log-http-transaction {}\n".format(policy['Log HTTP'])
            cli_command += "        set poolname {}\n".format(policy['Poolname'])
            cli_command += "        set groups {}\n".format(policy['Groups'])
            cli_command += "        set comments {}\n".format(policy['Comments'])
            cli_command += "        set ssl-ssh-profile {}\n".format(policy['SSL-SSH Profile'])
            cli_command += "        set dlp-sensor {}\n".format(policy['DLP Sensor'])
            cli_command += "    next\n"
            cli_commands.append(cli_command)
    return cli_commands

if __name__ == "__main__":
    cli_commands = csv_to_cli("fpx_policies.csv")
    for cli_command in cli_commands:
        print(cli_command)
