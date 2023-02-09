
import subprocess

def run_command(command):
    process = subprocess.Popen(command, stdout=subprocess.PIPE, shell=True)
    while True:
        output = process.stdout.readline()
        if output == '' and process.poll() is not None:
            break
        if output:
            print(output.strip().decode("utf-8"))

run_command("git pull")
run_command("git push")
