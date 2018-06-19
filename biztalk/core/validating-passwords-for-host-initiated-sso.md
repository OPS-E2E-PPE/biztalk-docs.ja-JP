---
title: ホストのパスワードを検証する側開始 SSO |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, host initiated [SSO]
- host initiated SSO, passwords
ms.assetid: 3cc1d68a-27ac-46ce-ba1e-21139a9df55e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03a33eb83630831863f231ff9594e3082f0faa98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287858"
---
# <a name="validating-passwords-for-host-initiated-sso"></a><span data-ttu-id="77cae-102">ホストのパスワードを検証する側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="77cae-102">Validating Passwords for Host Initiated SSO</span></span>
<span data-ttu-id="77cae-103">ホスト側開始 SSO の関連アプリケーションを作成するときは、Windows 以外のユーザーのパスワードの検証が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="77cae-103">When an affiliate application for host initiated SSO is created, password validation for the non-Windows user is enabled by default.</span></span> <span data-ttu-id="77cae-104">このため、アプリケーションでリソースにアクセスするための Windows ユーザー トークンを取得するために SSO を呼び出すときは、アプリケーションで Windows 以外のユーザー アカウントとパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77cae-104">This means when applications call SSO to obtain the Windows user token to access resources, they must provide the non-Windows user account and the non-Windows password.</span></span> <span data-ttu-id="77cae-105">パスワードが SSO データベースに格納されている、その Windows 以外のユーザーのパスワードと一致しない場合は、アクセスが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="77cae-105">If the password does not match the password in the SSO database for that non-Windows user, access is denied.</span></span> <span data-ttu-id="77cae-106">関連アプリケーションのパスワードの検証機能は、必要に応じて無効にできます。</span><span class="sxs-lookup"><span data-stu-id="77cae-106">If necessary, the password validation feature can be disabled for the affiliate application.</span></span> <span data-ttu-id="77cae-107">パスワードの検証機能は、ホスト側開始 SSO の関連アプリケーションの種類が単独であっても、ホスト グループであってもどちらにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="77cae-107">The password validation feature applies to both individual and host group type affiliate applications for host initiated SSO.</span></span>  
  
 <span data-ttu-id="77cae-108">ホスト側開始 SSO 関連アプリケーションの種類が単独の場合の XML ファイルの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="77cae-108">An example XML file for Individual type host initiated SSO affiliate application is:</span></span>  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserGroupAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminGroupAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no"  configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 <span data-ttu-id="77cae-109">ホスト側開始 SSO の単独アプリケーションの場合、上記の appUserAccount は、Windows ドメイン アカウント ユーザーの一覧を含むグループ アカウントです。一覧の Windows ドメイン アカウント ユーザーは、それぞれ対応する Windows 以外のアカウントに 1 対 1 でマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="77cae-109">In the case of individual applications for host initiated SSO, the appUserAccount is a group account that contains the list of Windows domain account users that have a 1 to 1 mapping with their corresponding non-Windows accounts.</span></span>  
  
 <span data-ttu-id="77cae-110">ホスト側開始 SSO 関連アプリケーションの種類がホスト グループの場合の XML ファイルの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="77cae-110">An example XML file for host group type host initiated SSO affiliate application is:</span></span>  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminGroupAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags  configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 <span data-ttu-id="77cae-111">ホスト側開始 SSO のグループ アプリケーションでは、上記の appUserAccount を、個別のユーザー アカウントにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77cae-111">In group applications for host initiated SSO, the appUserAccount must be an individual user account.</span></span> <span data-ttu-id="77cae-112">このアカウントは、Windows 以外のアカウントがすべてマップされるアカウントです。</span><span class="sxs-lookup"><span data-stu-id="77cae-112">It is this account that all non-Windows accounts are mapped to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77cae-113">参照</span><span class="sxs-lookup"><span data-stu-id="77cae-113">See Also</span></span>  
 [<span data-ttu-id="77cae-114">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="77cae-114">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)