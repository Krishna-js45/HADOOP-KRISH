{
  "project": "Hadoop Installation on Windows 10 using WSL",
  "mode": "Single Node (Pseudo-distributed)",
  "audience": "Academic Lab / Seminar",
  "steps": [
    {
      "step": 1,
      "title": "Enable WSL on Windows",
      "platform": "Windows PowerShell (Admin)",
      "description": "Enable Windows Subsystem for Linux. This is a one-time setup per system.",
      "commands": [
        "wsl --install"
      ],
      "notes": [
        "Restart the system if prompted",
        "Do not interrupt the process"
      ],
      "success_condition": "System restarts successfully"
    },
    {
      "step": 2,
      "title": "Install Ubuntu on WSL",
      "platform": "Windows PowerShell",
      "description": "Install Ubuntu 20.04 LTS for Hadoop compatibility.",
      "commands": [
        "wsl --list --online",
        "wsl --install -d Ubuntu-20.04"
      ],
      "notes": [
        "Ubuntu may also be installed via Microsoft Store",
        "Choose Ubuntu 20.04 or 22.04 only"
      ],
      "success_condition": "Ubuntu terminal opens and asks for username and password"
    },
    {
      "step": 3,
      "title": "Create Linux User",
      "platform": "Ubuntu Terminal",
      "description": "Create a Linux user account (one-time).",
      "commands": [],
      "notes": [
        "Password will not be visible while typing",
        "Remember this password (used with sudo)"
      ],
      "success_condition": "Terminal prompt shows: username@machine:~$"
    },
    {
      "step": 4,
      "title": "Update Ubuntu Packages",
      "platform": "Ubuntu Terminal",
      "description": "Update system packages to avoid dependency issues.",
      "commands": [
        "sudo apt update",
        "sudo apt upgrade -y"
      ],
      "notes": [
        "This step avoids Java and Hadoop installation errors"
      ],
      "success_condition": "Commands complete without errors"
    },
    {
      "step": 5,
      "title": "Install Java (Required for Hadoop)",
      "platform": "Ubuntu Terminal",
      "description": "Install Java 11. Hadoop runs on the Java Virtual Machine.",
      "commands": [
        "sudo apt install openjdk-11-jdk -y"
      ],
      "notes": [
        "Java 8 or Java 11 only",
        "Do NOT install Java 17 or newer"
      ],
      "success_condition": "Java installation completes successfully"
    },
    {
      "step": 6,
      "title": "Verify Java Installation",
      "platform": "Ubuntu Terminal",
      "description": "Verify that Java is correctly installed.",
      "commands": [
        "java -version"
      ],
      "expected_output": "openjdk version \"11\"",
      "success_condition": "Java version is displayed"
    }
  ]
}

