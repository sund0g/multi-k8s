### Table of Contents

* [Section 16: Kubernetes Production Deployment](#16)

<a name="16"></a>
## Section 16: Kubernetes Production Deployment

#### Lesson 221

* The steps to promoting the **complex** application to a **production** deployment consists of the following steps,

	1. Create a **GitHub repo**
	2. Connect the repo to **Travis CI**
	3. Create a **Google Cloud Project**
	4. Enable **billing** for the project
	5. Add **deployment scripts** to the repo.

	> Unlike **AWS** there is no **free** tier with **GCP** so there will be a minimal charge for this part of the course.
	> 
	> This is why all the non-GCP tasks are being completed before the GCP project is created.

* The **[GCP Pricing Calculator](https://cloud.google.com/products/calculator/)** can be used to estimate the costs to be incurred as follows,
	1. Select the **Kubernetes Engine** at the top of the page.
	2. Set the **number of nodes** to **3**
	3. Leave the other options unchanged.
	4. Scroll down and select **ADD TO ESTIMATE**
	5. Scroll to the **Persistent Disk** section.
	6. Set the **persistent disk storage** to **2GB** and **ADD TO ESTIMATE**.
	7. Scroll to the **Load Balancing** section.
	8. Set **Number of Forwarding Rules** to **1**.
	9. Set **Network Traffic Processed** to **100MB**.

	The estimate should be around **$92.00/month**. To keep costs as low as possible, complete this section in **less than 24 hours**.

#### Lesson 222

* Why is **Google Cloud Platform** being used as the cloud provider for this section?

	1. AWS only started supporting k8s on 2018; ease of use not there yet.
	2. GCP has a more robust environment for k8s.
	3. GCP has excellent documentation.

	> **GCP** also provides a **cloud console** which is essentially a terminal instance connected to the VPC. this provides a **kubectl** that is directly connected to the production environment.

#### Lesson 223

* To begin the process of migration the app to a **production environment**, create the **multi-k8s** repository.

> Can do this either via the web UI or the command line. I opted for the Web UI. If doing from the command line, may need to refer to the video for details.

#### Lesson 224

* To connect **Travis CI** with the **multi-k8s** repo,

	1. Navigate to **[Travis CI](https://travis-ci.org/)**
	2. Go to **Profile | Settings**
	3. Click the **Sync account** button and verify the **multi-k8s** repo is listed in the dashboard.
	4. Select the **slider** on the left to enable builds for the repo.

	> I had to log out of Travis and back in before the **multi-k8s** repo was listed in the dashboard.
	
#### Lesson 225


