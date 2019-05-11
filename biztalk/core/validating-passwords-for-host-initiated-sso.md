---
title: ホストのパスワードを検証側開始 SSO |Microsoft Docs
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
ms.openlocfilehash: 6ac003083157c69be0fcabaeb37ff7064b76a6e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279563"
---
# <a name="validating-passwords-for-host-initiated-sso"></a><span data-ttu-id="0fda0-102">ホストのパスワードを検証側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="0fda0-102">Validating Passwords for Host Initiated SSO</span></span>
<span data-ttu-id="0fda0-103">ホスト側開始 SSO が作成される関連アプリケーションは、ときに Windows 以外のユーザーのパスワードの検証は既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="0fda0-103">When an affiliate application for host initiated SSO is created, password validation for the non-Windows user is enabled by default.</span></span> <span data-ttu-id="0fda0-104">このため、アプリケーションがリソースにアクセスする Windows ユーザー トークンの取得に SSO を呼び出すと、Windows 以外のユーザー アカウントと非 Windows パスワードを提供する必要があります、します。</span><span class="sxs-lookup"><span data-stu-id="0fda0-104">This means when applications call SSO to obtain the Windows user token to access resources, they must provide the non-Windows user account and the non-Windows password.</span></span> <span data-ttu-id="0fda0-105">パスワードがその Windows 以外のユーザーの SSO データベースにパスワードが一致しない場合は、アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="0fda0-105">If the password does not match the password in the SSO database for that non-Windows user, access is denied.</span></span> <span data-ttu-id="0fda0-106">必要に応じて、関連アプリケーションのパスワードの検証機能を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0fda0-106">If necessary, the password validation feature can be disabled for the affiliate application.</span></span> <span data-ttu-id="0fda0-107">パスワードの検証機能は、個人の両方に適用され、ホスト グループ タイプの関連アプリケーションのホスト側開始 SSO。</span><span class="sxs-lookup"><span data-stu-id="0fda0-107">The password validation feature applies to both individual and host group type affiliate applications for host initiated SSO.</span></span>  
  
 <span data-ttu-id="0fda0-108">XML ファイルの例の個々 の型のホスト側開始 SSO 関連アプリケーションは。</span><span class="sxs-lookup"><span data-stu-id="0fda0-108">An example XML file for Individual type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="0fda0-109">個々 のアプリケーションの場合ホスト側開始 SSO を上記の appUserAccount は、グループ アカウントの 1 対 1 マッピングが、対応する Windows 以外のアカウントである Windows ドメイン アカウントのユーザーの一覧を含むです。</span><span class="sxs-lookup"><span data-stu-id="0fda0-109">In the case of individual applications for host initiated SSO, the appUserAccount is a group account that contains the list of Windows domain account users that have a 1 to 1 mapping with their corresponding non-Windows accounts.</span></span>  
  
 <span data-ttu-id="0fda0-110">XML ファイルの例の開始された SSO 関連アプリケーションのホスト グループ タイプのホストは。</span><span class="sxs-lookup"><span data-stu-id="0fda0-110">An example XML file for host group type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="0fda0-111">グループ アプリケーションのホスト側開始 SSO の、上記の appUserAccount は個々 のユーザー アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fda0-111">In group applications for host initiated SSO, the appUserAccount must be an individual user account.</span></span> <span data-ttu-id="0fda0-112">Windows 以外のすべてのアカウントにマップされるこのアカウントになります。</span><span class="sxs-lookup"><span data-stu-id="0fda0-112">It is this account that all non-Windows accounts are mapped to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fda0-113">参照</span><span class="sxs-lookup"><span data-stu-id="0fda0-113">See Also</span></span>  
 [<span data-ttu-id="0fda0-114">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="0fda0-114">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)