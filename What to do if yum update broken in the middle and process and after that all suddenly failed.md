Scenario:

1. You do `yum update`
2. After that the process killed because of out of memory
3. You add more RAM (my case is upgrade the EC2 instance)
4. You do `yum update` again and suddenly many errors happen, usually because of duplicate package bla bla bla
5. Relax
6. Just rpm -e --justdb <package-version> (package-version is the package version that usually higher or latest because of previously updated before the broken happen)
7. Do again `yum update`
8. Problem gone
