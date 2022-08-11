# Cloudformation Template

## Prerequisite
1. AWS CLI should be installed.


### To deploy the platform stack
  >$ aws cloudformation deploy --template platform-cf.yml --stack-name &lt;stack-name&gt; --region &lt;region&gt; --parameter-overrides  WebsiteDNS=&lt;website-url&gt; HostedZoneId=&lt;hostedzone-id&gt;  --profile &lt;profile-name&gt;
  
  For Example:
  >$ aws cloudformation deploy --template platform-cf.yml --stack-name shop-platform-prod-0 --region us-east-1 --parameter-overrides WebsiteDNS=raisethebarawards.in HostedZoneId=XXNNXXXNNXXXX --profile beslin

Where:
- --stack-name - name of the stack
- --region - pass the region in which stacks needs to be deployed
- WebsiteDNS - pass the DNS 
- HostedZoneId - DNS hostedzoneid


### To deploy the external shop stack
  >$ aws cloudformation deploy --template external-shop-cf.yml --stack-name &lt;stack-name&gt; --region &lt;region&gt; --parameter-overrides WebsiteDNS=&lt;website-url&gt; ExternalDomainDNS=&lt;website-url&gt; --profile &lt;profile-name&gt;
  
  For Example:

  > aws cloudformation deploy --template external-shop-cf.yml --stack-name shop-platform-prod-1 --region us-east-1 --parameter-overrides WebsiteDNS=www.raisethebarawards.in ExternalDomainDNS=t1.raisethebarawards.in HostedZoneId=Z0720484OLK2M9TQTNXT --profile &lt;profile-name&gt;

Where:
- --stack-name - name of the stack
- --region - pass the region in which stacks needs to be deployed
- WebsiteDNS - pass the DNS 
- HostedZoneId - DNS hostedzoneid