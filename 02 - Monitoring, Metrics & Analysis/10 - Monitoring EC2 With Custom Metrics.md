# 10 - Monitoring EC2 With Custom Metrics

###### Scrips para monitoração

Documentação para o script (bootstrap)
http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/mon-scripts.html

- Instalação dos pacotes perl necessários
sudo yum install perl-Switch perl-DateTime perl-Sys-Syslog perl-LWP-Protocol-https -y


mkdir /CloudWatch
cd /CloudWatch

- Baixar o script (conforme orientação da documentação)
curl http://aws-cloudwatch.s3.amazonaws.com/downloads/CloudWatchMonitoringScripts-1.2.1.zip -O

unzip CloudWatchMonitoringScripts-1.2.1.zip
rm CloudWatchMonitoringScripts-1.2.1.zip
cd aws-scripts-mon

- Para verificar se a instancia esta conectando com o serviço do cloudwatch (precisa da role)
./mon-put-instance-data.pl --men-util --verify --verbose

- Para incluir no crontab

*/5 * * * * root /CloudWatch/aws-scripts-mon/mon-put-instance-data.pl --mem-util --mem-used --mem-avail

echo '*/5 * * * * root /CloudWatch/aws-scripts-mon/mon-put-instance-data.pl --mem-util --mem-used --mem-avail' >> /etc/crontab

cat /etc/crontab
