## How to install Gitlab server


### Clean up cached data
```angular2html
dnf clean all
```

### Update the AlmaLinux operating system
```angular2html
dnf update -y
```

### Install GitLab dependencies
```angular2html
dnf install curl policycoreutils-python-utils perl -y
```

### Download and add a GitLab repository
```angular2html
curl https://packages.gitlab.com/gitlab/gitlab-ce/gpgkey | sudo tee /etc/pki/rpm-gpg/RPM-GPG-KEY-gitlab
```
```angular2html
curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
```

### Installing GitLab via a package manager (RPM)
```angular2html
dnf install gitlab-ce -y
```

### Configure and reconfigure GitLab
```angular2html
vim /etc/gitlab/gitlab.rb
    external_url <ip / domain_url>
```

### Reconfigure GitLab
```angular2html
gitlab-ctl reconfigure
```

### Verify the current status
```angular2html
gitlab-ctl status
```

### Retrieve the root password
```angular2html
cat /etc/gitlab/initial_root_password
```