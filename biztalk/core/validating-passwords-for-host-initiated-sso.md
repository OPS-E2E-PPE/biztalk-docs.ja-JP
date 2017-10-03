---
title: "ホストのパスワードを検証する側開始 SSO |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, host initiated [SSO]
- host initiated SSO, passwords
ms.assetid: 3cc1d68a-27ac-46ce-ba1e-21139a9df55e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03a33eb83630831863f231ff9594e3082f0faa98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validating-passwords-for-host-initiated-sso"></a>ホストのパスワードを検証する側開始 SSO
ホスト側開始 SSO の関連アプリケーションを作成するときは、Windows 以外のユーザーのパスワードの検証が既定で有効になります。 このため、アプリケーションでリソースにアクセスするための Windows ユーザー トークンを取得するために SSO を呼び出すときは、アプリケーションで Windows 以外のユーザー アカウントとパスワードを指定する必要があります。 パスワードが SSO データベースに格納されている、その Windows 以外のユーザーのパスワードと一致しない場合は、アクセスが拒否されます。 関連アプリケーションのパスワードの検証機能は、必要に応じて無効にできます。 パスワードの検証機能は、ホスト側開始 SSO の関連アプリケーションの種類が単独であっても、ホスト グループであってもどちらにも適用されます。  
  
 ホスト側開始 SSO 関連アプリケーションの種類が単独の場合の XML ファイルの例を以下に示します。  
  
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
  
 ホスト側開始 SSO の単独アプリケーションの場合、上記の appUserAccount は、Windows ドメイン アカウント ユーザーの一覧を含むグループ アカウントです。一覧の Windows ドメイン アカウント ユーザーは、それぞれ対応する Windows 以外のアカウントに 1 対 1 でマッピングされます。  
  
 ホスト側開始 SSO 関連アプリケーションの種類がホスト グループの場合の XML ファイルの例を以下に示します。  
  
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
  
 ホスト側開始 SSO のグループ アプリケーションでは、上記の appUserAccount を、個別のユーザー アカウントにする必要があります。 このアカウントは、Windows 以外のアカウントがすべてマップされるアカウントです。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)