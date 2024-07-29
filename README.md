# ExternalCollab-EntraB2B
This solution design implement OneDrive/SharePoint external sharing using Entra ID B2B
# 🌟 OneDrive External Sharing with Entra ID B2B Integration

## 🎯 Overview

Enable secure file sharing with external users using OneDrive and Entra ID B2B. It's like giving your files superpowers! 🦸‍♂️

## 🏗️ Architecture

Here's how the magic happens:

![Architecture Diagram](architecture-diagram.svg)

## 🛠️ Prerequisites

- Microsoft 365 tenant (with admin superpowers 🦸‍♀️)
- SharePoint Online Management Shell (your command center 🖥️)
- Entra ID Premium P1 or P2 license (for fancy Conditional Access 🎭)

## 🚀 Quick Setup

1. **Create Staff Group** 👥
   - Make a new group in Entra admin center
   - Give them the "Guest Inviter" role (VIP access! 🎟️)

2. **Enable External Sharing** 🌍
   - In Entra admin center, go to External Identities > External collaboration settings
   - Set guest access and invite settings (be generous, but safe! 🛡️)

3. **Configure SharePoint Sharing** 📂
   - In SharePoint admin center, set org-level and site-level sharing
   - Choose "Anyone" or "New and existing guests" (your call, boss! 🧐)

4. **Set Up MFA for Guests** 🔐
   - Create a Conditional Access Policy in Entra admin center
   - Require MFA for all guest users (double the security, double the fun! 🎉)

5. **Enable Entra B2B Integration** 🤝
   - Run this magical PowerShell command:
     ```powershell
     Set-SPOTenant -EnableAzureADB2BIntegration $true
     ```

## 🎬 How It Works

1. Staff shares file 📤
2. Guest gets registered in Entra ID 📝
3. Guest receives email with link 📧
4. Guest clicks link, logs in (first-timers register) 🖱️
5. Guest completes MFA challenge 🔑
6. Guest accesses the file. Voila! 🎉

## 🛡️ Security Tips

- Review guest access regularly (spring cleaning, but for permissions 🧹)
- Monitor sharing activities (be the watchful guardian 👀)
- Educate your users (knowledge is power! 💪)

## 🆘 Troubleshooting

If things go wonky:
- Check all your settings (twice! ✅✅)
- Verify licenses (no freeloaders allowed 🚫)
- Review those Conditional Access Policies (they can be sneaky 🕵️‍♂️)

## 📚 Learn More

- [Entra External ID docs](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/)
- [SharePoint external sharing](https://learn.microsoft.com/en-us/sharepoint/external-sharing-overview)
- [B2B Conditional Access](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/conditional-access)

Happy sharing! 🎊
