# monitoring-system-
simple linux monitoring system 
#!/bin/bash

echo "=== System Monitoring Report ==="
echo "Date: $(date)"
echo ""

# CPU Load
echo "--- CPU Load ---"
uptime
echo ""

# Memory Usage
echo "--- Memory Usage ---"
free -h
echo ""

# Disk Usage
echo "--- Disk Usage ---"
df -h | grep -v tmpfs
echo ""

# Top 5 Processes by CPU
echo "--- Top 5 Processes (CPU) ---"
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head -6
echo ""

# Top 5 Processes by Memory
echo "--- Top 5 Processes (Memory) ---"
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem | head -6
echo ""

# Network Connections
echo "--- Active Network Connections ---"
ss -tunap | head -10
echo ""
