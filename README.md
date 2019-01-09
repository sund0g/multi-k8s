### Table of Contents

* [Section 16: Kubernetes Production Deployment](#16)

<a name="16"></a>
## Section 16: Kubernetes Production Deployment

#### Lesson 221

* Promoting the **complex** application to a **production** deployment consists of the following steps,

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

* How to get free [Google Cloud Credits](https://console.cloud.google.com/freetrial/signup/0) if this is the first time working with **GCP**. (Not valid for existing accounts).

#### Lesson 226

> **IMPORTANT: This is where the Google Cloud project is created, thus the beginning of incurring charges.** Do not create the project until ready to complete the remaining lessons in this section in as short time as possible.

* To create the **project**,

	1. Navigate to the **[Google Cloud Console](https://console.cloud.google.com)**
	2. Select the **project selector** dropdown (at the top left).
	3. Select the "New Project" button on the top right of the messagebox.
	4. Enter **"multi-k8s"** as the **project name**
	5. Click **Create**. It may take a few seconds to create the project.

#### Lesson 227

* To link a **billing account**,

	1. Select the **multi-k8s** project from the **project selector** dropdown.
	2. Select **Billing** from the **Navigation menu** (top left).

		> The following steps can be skipped if the **billing account** has been previously configured.
		
	3. Click **Link a billing account**
	4. Follow the **wizard** steps to create an account.
	5. Set the account for the **multi-k8s** project.

	This should result is the dashboard showing the project linked to billing account.
	
#### Lesson 228

* To create a new **k8s Cluster**,

	1. Scroll down the **navigation menu** to the **Compute** section
	2. Select **Kubernetes Engine**
		
		> If an enable billing message returns, try refreshing the browser window. If that doesn't work, try to link the billing account again.

#### Lesson 229
