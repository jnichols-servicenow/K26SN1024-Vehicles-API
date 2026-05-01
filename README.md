# Vehicle Management — Demo Application used for K26

A scoped ServiceNow application used as the teaching application for **SNU1024: Securing a Scripted REST API** at Knowledge 2026. This application exposes a Scripted REST API (`vehicles_api`) for CRUD operations against the Vehicle (`x_snc_vehicle_ma_0_vehicle`) table and is the target of the labs covering authentication, OAuth 2.0, ACLs, API Access Policies, API Rate Limits, and other security measures.

Application scope: `x_snc_vehicle_ma_0`

> ⚠️ **Learning resource only.** This application is deliberately built with weaknesses and progressive hardening steps that are introduced across the lab exercises. Do not deploy it to a production instance. This application is covered by the MIT License.

---

## Table of contents

- [About this repository](#about-this-repository)
- [Prerequisites](#prerequisites)
- [Required plugins](#required-plugins)
- [Import method 1 — Import application using ServiceNow Studio](#import-method-1-—import-application-using-servicenow-studio)
- [Import method 2 — Download the update set and import app into your PDI](#import-method-2-—download-the-update-set-and-import-app-into-your-pdi)
- [Verify the installation](#verify-the-installation)
- [Lab materials](#lab-materials)
- [Support](#support)
- [License](#license)

---

## About this repository

This repository contains:

- The `Vehicle Management` scoped application source.
- Under Releases:
  - `SNU1024-VehicleManagement-App-v1.0.0.xml` - The Vehicle Management application packaged as an update set (also contains demo vehicle records).
  - `SNU1024-VehicleManagement-DemoVehicles-v1.0.0.xml` - Demo vehicle data packaged as an update set.
  - `SNU1024-VehicleManagement-DemoUsersAndGroups-v1.0.0.xml` - Demo user and group data packaged as an update set.

---

## Prerequisites

Before you begin, make sure you have:

- A **ServiceNow Personal Developer Instance (PDI)**. Zurich release or later. If you don't have one, request one at <https://developer.servicenow.com>.
- The **admin role** on your PDI.
- A **GitHub account** with the ability to fork public repositories.

---

## Required plugins

Install the following plugins on your PDI **before** importing the application. 

For PDIs, plugins can be activated using the Developer portal under **Manage my instance**. For other instances, use **Application Manager**.

| Plugin name | Plugin ID | Purpose |
|---|---|---|
| Explicit Roles | com.glide.explicit_roles | Installs the snc_external and snc_internal roles to demarcate between internal and external users in the ServiceNow instance. |
| REST APIs - Explicit Roles | com.glide.rest.explicit_roles | *Automatically installed with com.glide.explicit_roles* |

---

## Import method 1 — Import application using ServiceNow Studio

Forking creates your own copy of this repo under your GitHub account. You then import the forked copy into your PDI.

1. On the Select the **Fork** button in the top-right corner and follow the instructions.
2. On your fork's page, click the green **Code** button and copy the **HTTPS** URL — you'll paste it into ServiceNow Studio in the next step.
3. Log in to your PDI as a user with the `admin` role.
4. In the Application Navigator, search for and open **ServiceNow Studio**.
5. Select **Create → Import app**.
2. In the **Import app from source control** page, provide:
   - **URL** — the HTTPS URL of your fork from Step 2.
   - **Branch** — `main` (or the branch you want to import).
   - **Credential** — your GitHub credential.
3. Click **Import app**.

Studio will pull the application source from GitHub and create the scoped application `x_snc_vehicle_ma_0` on your PDI. 

See to import demo data.

## Import method 2 — Download the update set and import app into your PDI

1. Navigate to [Releases](https://github.com/jnichols-servicenow/K26SN1024-Vehicles-API/releases).
2. Download the `SNU1024-VehicleManagement-App-v1.0.0.xml` update set.
3. Go to **System Update Sets → Retrieved Update Sets** and upload, preview and commit the update set.

---

## Import demo data

The Vehicle Management application does not contain demo data. However, the application update set above does contain *vehicle* demo data. The [Releases](https://github.com/jnichols-servicenow/K26SN1024-Vehicles-API/releases) page contains the update set for vehicle demo data (if importing the app via ServiceNow Studio), and another update set containing user and group demo data. See [About this repository](#about-this-repository). Download and import as required. 

> NOTE:
> The application contains a testing page that is pre-configured to use the demo user accounts.

## Verify the installation

After the import completes, confirm the application is working:

1. In the PDI, navigate to to **Vehicles**.
2. **Vehicles → All** The **Vehicle** table. The demo data contains 10 sample records.
3. **Vehicles → Users** The **User** table. The demo data contains 4 sample records.
4. **Vehicles → Testing** The **Testing** page that allows you to quickly test your lab work. 
   Navigate to **Lab 1: Table settings → Lab 1a** and select **Test it** to confirm the Vehicles API is working. You should receive a `200 OK` response with a JSON payload describing a vehicle record.
   You can also copy the code and run it from a terminal on your local machine.

---

## Lab materials

The full lab guide for **SNU1024: REST API Security and Integration** is published on GitBook:

📖 [SNU1024 Lab Guide — GitBook](https://app.gitbook.com/o/wXJhB7H8YqI7f2lOgBuI/s/zOTeBR9y3RlMJ4cIdPem/)

The GitBook covers all nine labs:

1. Table settings
2. Access controls I
3. Access controls II
4. Access controls III
5. OAuth 2.0
6. Authentication scopes
7. API Access Policies
8. API rate limits
9. Disable deprecated versions

---

## Support

This is sample educational content and is provided **as-is** with no guarantee of support. Please fork to your own account for lab use. Pull requests are not accepted.

- For questions about the lab content, refer to the [Lab Book](https://app.gitbook.com/o/wXJhB7H8YqI7f2lOgBuI/s/zOTeBR9y3RlMJ4cIdPem/).
- For ServiceNow platform questions, see the [ServiceNow Developer Portal](https://developer.servicenow.com) and [ServiceNow Community](https://community.servicenow.com).

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

This application is intended solely for ServiceNow training and educational purposes. It is not hardened for production use and should not be deployed on production ServiceNow instances. Students and instructors are welcome to fork, modify, and adapt the code for learning.

---

*Author: Jason Nichols*

*Knowledge 2026 — SNU1024*
