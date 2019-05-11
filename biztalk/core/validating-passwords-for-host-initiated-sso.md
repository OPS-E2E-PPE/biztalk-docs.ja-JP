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
# <a name="validating-passwords-for-host-initiated-sso"></a>ホストのパスワードを検証側開始 SSO
ホスト側開始 SSO が作成される関連アプリケーションは、ときに Windows 以外のユーザーのパスワードの検証は既定で有効にします。 このため、アプリケーションがリソースにアクセスする Windows ユーザー トークンの取得に SSO を呼び出すと、Windows 以外のユーザー アカウントと非 Windows パスワードを提供する必要があります、します。 パスワードがその Windows 以外のユーザーの SSO データベースにパスワードが一致しない場合は、アクセスが拒否されました。 必要に応じて、関連アプリケーションのパスワードの検証機能を無効にできます。 パスワードの検証機能は、個人の両方に適用され、ホスト グループ タイプの関連アプリケーションのホスト側開始 SSO。  
  
 XML ファイルの例の個々 の型のホスト側開始 SSO 関連アプリケーションは。  
  
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
  
 個々 のアプリケーションの場合ホスト側開始 SSO を上記の appUserAccount は、グループ アカウントの 1 対 1 マッピングが、対応する Windows 以外のアカウントである Windows ドメイン アカウントのユーザーの一覧を含むです。  
  
 XML ファイルの例の開始された SSO 関連アプリケーションのホスト グループ タイプのホストは。  
  
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
  
 グループ アプリケーションのホスト側開始 SSO の、上記の appUserAccount は個々 のユーザー アカウントである必要があります。 Windows 以外のすべてのアカウントにマップされるこのアカウントになります。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)