# OTP Relay

> Seamlessly Integrate SMS OTP Verification with OTPRelay

OTP Relay is a self-hosted platform that reads all allowed SMS from your target device and sends them to a centralised server where your team members can read and perform authorised actions. This eliminates the need to be online at all times and increases productivity time. Additionally, with the integration and integration infrastructure, SMS OTP verification can be integrated into non-interactive CI tests such as Github Actions.

# Problem Statement

Developing and testing features requiring phone number verification (via SMS OTP) can be a frustrating and time-consuming process.  Two major challenges arise: limited testing environment with cheap SMS services lacking sandbox accounts, and the need for manual intervention when relying on personal phone numbers. This can lead to delays due to waiting for someone to be online to receive and provide the OTP, timeouts causing test failures, and privacy concerns for developers hesitant to use their personal numbers.

## Key Pain Points

The problem statement stems from my personal experience, when I have to wait for my team managers to come online before they can share the OTP with me. From the problem statement, I have created some pain points that we need to solve for the end-users.
- Developers face difficulties in implementing end-to-end tests for components reliant on SMS-based OTP verification due to the absence of common interfaces such as webhooks or code-level notifications.
- Developers may hesitate to provide their own phone numbers for receiving OTPs, leading to the use of alternative numbers such as those belonging to product managers. However, this reliance introduces dependencies on the availability of these individuals and delays in receiving OTPs, hindering development and testing progress.
- Time zone differences between developers and stakeholders contribute to delays in obtaining OTPs for testing purposes. These delays again generally disrupt development workflows and prolong testing cycles, impacting project timelines and delivery schedules.

# Solution

The solution for automated SMS delivery is already being developed by several developers across the globe. You can find these applications as “**Disposable SMS services**” on google search. The key idea is to build an application that would read the SMS and show it on the dashboard and which is accessible to the developers or users who want to use that OTP.
The issue with current solutions lies in their public dashboards, allowing anyone to access SMS content, posing privacy concerns, especially for private or staging dashboards. Additionally, these services lack control mechanisms, leading to the publication of all messages, increasing noise and hindering project focus. Moreover, when sender names are identical, such as SMS from banks or Amazon, filtering becomes challenging, further complicating project management.

## How OTP Relay is Different?

OTP Relay enhances existing solutions by introducing features such as **notications** via webhooks and websockets, **advanced message filtering**, and support for **multiple devices**. Its open-source nature empowers teams to host their instances (self-hosted), ensuring privacy and control.
Integration with webhooks and websockets streamlines testing, facilitating swift SMS notification receipt for non-interactive test cases, ideal for continuous integration pipelines. Additionally, plans for implementing generic extractors to extract OTP digits from the received message to save the development time and cost.
While a web dashboard is on the horizon, OTP Relay primarily operates through mobile applications along with **integrations for Slack channels and emails**, simplifying feature and configuration management.

> [!NOTE]
> Development related information and tech stack will be discussed later. But in the backend, I am planning to use either Nodejs+Fastify or Nestjs. Regarding the mobile application developer
