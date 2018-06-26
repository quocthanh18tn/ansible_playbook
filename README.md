learn about playbook ansible

---

- hosts: all    //chay cac may ao
  become: yes    //chay quyen root
  roles:         //cau truc file nhu v, sau khi vagrant up se run general main.yml
    - general


    ---

#- name: Update apt cache  #title show ra cho coi
#  command: apt update

- name: Install NGINX web server
#  apt: name=nginx state=present
  apt:
    name: nginx            //argument
    state: present
    update_cache: yes        //apt-get update



- name: Install htop
#  apt: name=nginx state=present
  apt:
    name: htop
    state: present


create ansible folder co cau truc :
├── provisioning
│   ├── group_vars
│   │   └── all
│   ├── playbook.yml
│   └── roles
│       └── general
│           └── tasks
│               └── main.yml
├── README.md
└── Vagrantfile


mkdir-p provisioning/{group_vars,roles}
mkdir-p provisioning/roles/general/taks
touch provisioning/group_vars all
touch provisioning playbook.yml
touch provisioning/roles/general/tasks main.yml


