# shiftstack-demo
For running a single openstack node (packstack) with openshift on top

1. Deploy CentOS stream, preferrably Centos Stream 8.
2. Start with this guide: https://www.rdoproject.org/install/packstack/ 
3. You will need to setup the network bridge in most cases, so make sure you follow this guide too: https://www.rdoproject.org/networking/neutron-with-existing-external-network/
4. Somewhere you will need an external DNS to setup the API and ingress records. I used dnsmasq on my ubiqiti home router
5. You can create the clouds.yaml file in ~/.config/openstack/clouds.yaml
6. Do the rest using the openshift installer, it is important to have that external networking for this to be successful. Do not skip step 3.

Notes:
- I modified the quota of my openstack project "shiftstack" with 48 cores.
- Ensure you have a large root partition. I had to reinstall from the default of 70GB it was not enough to create OCP cluster locally. Next time I used 1.5 TB for the root partition ('/'). All other values such as swap are created as per normal.
