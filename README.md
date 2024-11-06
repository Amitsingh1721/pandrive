import os

def scan_files(directory):
    print(f"Scanning {directory} for suspicious files...")
    malicious_files = []
    
    for root, dirs, files in os.walk(directory):
        for file in files:
            if file.endswith('.exe') or file.endswith('.dll'):
                malicious_files.append(os.path.join(root, file))
    
    if malicious_files:
        print("Suspicious files found:")
        for file in malicious_files:
            print(file)
    else:
        print("No suspicious files found.")

scan_files("C:\\")
print("Hello, this is a test script.")

