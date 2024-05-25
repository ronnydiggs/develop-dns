<p align="center">
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/b6484435-0a0c-429a-bfa4-c129dc4f9f71" width="250"/>
</p>

<h1>Domain Name System - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the Domain Name System Lab. 
Need to have AD installed on a domain controller and a client VM before proceeding.
Check the Configuring Active Directory Lab.
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Client VM
- Active Directory VM

<h2>Operating Systems Used </h2>

- Windows 10</b> 
- Windows Server 2022</b> 

<h2>A-Record Exercise</h2>

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/e5bb576a-754f-4dbe-914c-1f9989b09822" width="400"/>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/9b898efa-c5ed-4d6f-b5ec-28fbecd57694" width="400"/>
</p>
<p>
Log into DomainController as the domain admin account (mydomain.com\ronny)
</p>
<p>
Log into Client1 as admin as well (mydomain.com\ronny)
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/556c9695-1503-43c9-9bd2-8574a500f419" width="500"/>
</p>
<p>
In command prompt, ping mainframe. Then nslookup mainframe.
Notice that they both fail because of no DNS record.
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/368043a9-0d90-4707-b410-7c73a42af838" width="400"/>
<img src="" width="400"/>
</p>
<p>
Create a DNS A-record on DomainController and point it to DomainController's private IP address: 10.0.0.5.
We are mapping the name mainframe to the IP address 10.0.0.5 in the forward lookup zone in the domain controller.
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/85f816b0-3ca9-43b3-b67b-e6566b832bd5" width="400"/>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/170d05de-dce7-4c22-9476-0dd1a2f4a5a4" width="400"/>
</p>
<p>
Go to Client 1, ping mainframe and nslookup mainframe.
</p>
<br />

<h2>Local DNS Cache Exercise</h2>

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/96ffb19e-07a9-4eac-8511-2b22362c5363" width="400"/>
</p>
<p>
Change mainframe's record address to 8.8.8.8
</p>
<br />
<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/222b6a28-1819-44b7-8b79-bf64ba37c458" width="400"/>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/71b8e734-56b4-4cc3-92f4-f435850ab2ed" width="400"/>
</p>
<p>
In Client 1, ping mainframe. Notice that it still pings the old address. That is because the dns cache has not changed. Type ipconfig /displaydns
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/54beda9d-200c-4404-ad5f-c97f7be1d94b" width="400"/>
</p>
<p>
Type ipconfig /flushdns. Notice the empty cache. Type ping mainframe.
</p>
<br />

<h2>CNAME Record Exercise</h2>

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/bd4a4c43-ab80-43a7-a31a-bf8410842efc" width="400"/>
</p>
<p>
Create a CNAME Record that maps the word search to www.google.com
</p>
<br />

<p>
<img src="https://github.com/ronnydiggs/develop-dns/assets/64152064/7d2e80ff-a4bf-4d34-818e-87a7732e1984" width="400"/>
</p>
<p>
On Client 1, ping search and nslookup search. 
</p>
<br />
