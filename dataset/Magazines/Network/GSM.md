<h2 align="center">CEH</h2>
**<p align="center">learning URLs: <a href="https://youtu.be/Pn57NWq4o_w?si=NYcKaHxB49DtY4xW">jadi</a></p>**

---
### 1. **Main Components of the GSM Network**
#### **MS (Mobile Station) - Mobile Phone:**
   - The **Mobile Station** is the user's mobile phone, which connects to the GSM network and facilitates communication.
   - **SIM (Subscriber Identity Module)**: The SIM card identifies the subscriber and contains information like the phone number and security data.

#### **BTS (Base Transceiver Station):**
   - The BTS is responsible for wireless communication with mobile devices. It includes antennas and radio equipment, and each BTS covers a specific geographic area known as a "cell."

#### **BSC (Base Station Controller):**
   - The BSC manages several BTSs. It handles tasks such as handoff between BTSs, radio resource management, and power control.

#### **MSC (Mobile Switching Center):**
   - The MSC is the central part of the network, responsible for switching calls between users and managing communication with other networks (such as landlines or the internet).
   - The MSC also handles user location, manages incoming and outgoing calls, and controls roaming.

#### **HLR (Home Location Register):**
   - A database that stores the permanent details of subscribers, such as phone numbers, active services, and the current location of the subscribers.

#### **VLR (Visitor Location Register):**
   - A temporary database that stores information about users roaming in a specific area. When a user enters a new region, their details are registered in the VLR.

#### **AuC (Authentication Center):**
   - This center authenticates users to prevent unauthorized access to the network. It stores security data like encryption keys.

#### **EIR (Equipment Identity Register):**
   - This part of the network stores information about the identity of mobile phones (IMEI) and helps detect stolen or unauthorized devices.

### 2. **How GSM Networks Work**
GSM networks are designed using a cellular architecture, meaning the geographic area is divided into smaller cells, each covered by a BTS.

#### **Initial Connection:**
   1. When the mobile phone is turned on, it connects to the nearest BTS.
   2. The mobile phone authenticates the user through the SIM card using the AuC.
   3. If the user is authenticated, their details are stored in the HLR or VLR.

#### **Making Calls or Sending SMS:**
   1. When a user initiates a call or sends an SMS, the request is sent to the BTS and then relayed to the BSC and MSC.
   2. The MSC decides where to route the call (inside or outside the GSM network).
   3. If the call needs to be routed to another network (e.g., a landline), the MSC manages the transfer.

#### **Hand-off During Movement:**
   - When a user moves out of the coverage area of one BTS, the BSC manages the hand-off process to transfer the connection to another BTS without dropping the call.

### 3. **GSM Radio Technology**
   - **FDMA (Frequency Division Multiple Access)**: The radio spectrum is divided into different frequency bands, with each band assigned to a call.
   - **TDMA (Time Division Multiple Access)**: Each frequency band is divided into time slots so multiple users can share the same frequency.

### 4. **Encryption and Security:**
   - GSM uses encryption to protect user data. This encryption is managed by the AuC using specific algorithms.
   - To prevent eavesdropping, conversations and messages are encrypted.

### 5. **Roaming:**
   - When a user travels to an area outside their home network's coverage, the visited network registers the user in its VLR, allowing them to continue using services.

### 6. **Data Services and Internet:**
   - Initially, GSM was designed for voice communication, but it later evolved to support data services. GSM uses **GPRS** and **EDGE** technologies for mobile internet data transmission.

### 7. **Evolution to Newer Generations:**
   - As the demand for higher speed and capacity increased, GSM networks were upgraded to newer generations such as **3G**, **4G**, and **5G**. However, GSM remains the foundation for these advancements.

### Conclusion:
GSM networks, one of the earliest and most widely used mobile technologies, enable communication between billions of users. By using base stations, controllers, and central switching systems, GSM facilitates voice calls, SMS, and data services between mobile users.

---