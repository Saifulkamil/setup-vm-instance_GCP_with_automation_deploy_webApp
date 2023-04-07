# setup-vm-nstance_GCP_with_automation_deplot_webApp

    node -v  //to see the version, if node if node not found then it must be install node js (the node js installed is version 19.xx) 
    sudo apt update     // the syntax for update system vm-intance
    sudo curl -fsSL https://deb.nodesource.com/setup_19.x | bash - && apt-get install -y nodejs    // the syntax for install the node js
    git --version     // the syntax for chek version of git if git not found then must be installed git
    sudo apt-get install git -y     // the syntax for install the git 
    sudo git clone https://github.com/sepol-sys/express_js.git /home/c065dsx0772/web/express_js.git && cd /home/c065dsx0772/web/express_js.git   // the syntax for clone repository project webApp to folder web/express_js.git and go to the folder
    sudo npm install    // after go to folder project webApp,run the following syntax path
    sudo npm run start-prod // and then run syntax for run the service web 

you can copy the syntax
    sudo apt update
    sudo curl -fsSL https://deb.nodesource.com/setup_19.x | bash - && apt-get install -y nodejs
    sudo apt-get install git -y
    sudo git clone https://github.com/sepol-sys/express_js.git /home/c065dsx0772/web/express_js && cd /home/c065dsx0772/web/express_js
    sudo npm install
    sudo npm run start

you can change the link git and folder to clone projeck 

the syntax below can be use for gcloud shell with one button enter

    gcloud compute instances create instance-example-for-web --project=my-project-belajar-gc14362 --zone=asia-southeast2-a --machine-type=e2-small --network-interface=network-tier=PREMIUM,subnet=default --metadata=startup-script=sudo\ apt\ update$'\n'sudo\ curl\ -fsSL\ https://deb.nodesource.com/setup_19.x\ \|\ bash\ -\ \&\&\ apt-get\ install\ -y\ nodejs$'\n'sudo\ apt-get\ install\ git\ -y$'\n'sudo\ git\ clone\ https://github.com/sepol-sys/express_js.git\ /home/c065dsx0772/web/express_js\ \&\&\ cd\ /home/c065dsx0772/web/express_js$'\n'sudo\ npm\ install$'\n'sudo\ npm\ run\ start --maintenance-policy=MIGRATE --provisioning-model=STANDARD --service-account=362304165619-compute@developer.gserviceaccount.com --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append --tags=web --create-disk=auto-delete=yes,boot=yes,device-name=instance-example-for-web,image=projects/debian-cloud/global/images/debian-11-bullseye-v20230306,mode=rw,size=10,type=projects/my-project-belajar-gc14362/zones/us-central1-a/diskTypes/pd-balanced --no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --labels=ec-src=vm_add-gcloud --reservation-affinity=any

service run on port 5000

how to access service webApp which has been deploy

    open browser type external ip from vm instace follwed by port

    external_ip:port 
    192.168.10.1:5000

but service webApp do not access because not yet make firewall for service webApp 


    gcloud compute --project=my-project-belajar-gc14362 firewall-rules create web --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:5000 --source-ranges=0.0.0.0/0 --target-tags=web

run the syntax on gcloud shell 

you can change name firewall, name tag, port, source and onther

and then yor service webApp running success
