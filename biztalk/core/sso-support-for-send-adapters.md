---
title: "送信アダプターの SSO のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d590ada6b8ee80c942714a698d0001c207ac6751
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-support-for-send-adapters"></a>送信アダプター用の SSO サポート
エンタープライズ シングル サインオン (SSO) には、ローカル、ネットワーク、およびドメインの境界間で暗号化されたユーザーの資格情報を格納および転送するサービスが用意されています。 トランスポート アダプターを作成する場合は、SSO API を利用して、トランスポート アダプターがバックエンドのアプリケーションにアクセスするために使用するユーザーの資格情報を処理できます。  
  
 SSO をサポートしないトランスポート アダプターは、通常、1 セットのバックエンド アプリケーションにアクセスするために使用する資格情報を使用して設定する必要があります。 多くのバックエンド システムの場合、単一のアカウント認証ではすべてのセキュリティの実施に対応できません。 多くのアプリケーションは、それらのアプリケーションにアクセスしているユーザーに応じて異なるアクセス権を提供します。 アダプターは、SSO を使用して、アクセスしようとしているユーザーに基づいてエンドポイントに使用する資格情報を動的に選択できます。  
  
## <a name="how-send-adapters-work-with-sso"></a>送信アダプターと SSO の連携  
 SSO をサポートするアダプターを検証し、チケットを引き換えるし、を使用して、SSO システムからユーザーの資格情報を取得送信、 **ISSOTicket.ValidateAndRedeemTicket** API です。 アダプターは、取得した資格情報を使用して送信先エンドポイントを認証します。  
  
 次のコードは、送信アダプターが SSO システムからユーザーの資格情報を取得する方法を示しています。  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                        IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_UserName = null;  
     private string m_UserPassword = null;  
  
 // Get user credentials from SSO  
 // AffiliateAppVal is the name of SSO affiliate   
 // application for the specific destination endpoint  
     private void GetUserCredentials(  
 IBaseMessage message,   
 string AffiliateAppVal )  
     {  
 string creds[] = null;  
 string externalUserName = null;  
  
 ISSOTicket ssoTicket = new ISSOTicket();  
 creds = ssoTicket.ValidateAndRedeemTicket(  
 message,   
 AffiliateAppVal,   
 0,   
 out externalUserName);  
  
 m_UserName = externalUserName;  
 m_UserPassword = creds[0];  
     }  
...  
}  
```  
  
## <a name="party-resolution"></a>パーティの解決  
 パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ ID (SID) を、対応する構成済み BizTalk Server パーティにマップします。 この情報が使用できるようにするアダプターがコンテキスト プロパティには、2 つのシステム メッセージの設定する必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決が使用します。構成されている場合のコンポーネント。  
  
 **WindowsUser**プロパティには、たとえば redmond\myBtsUser、送信者のドメイン ユーザーが設定されます。 **SignatureCertificate**プロパティには、クライアント認証証明書の拇印が設定されます。  
  
## <a name="managing-passwords"></a>パスワードを管理します。  
 エンドポイントのプロパティに直接資格情報を設定する場合、バインド ファイルをエクスポートする必要があるときはパスワード フィールドが空になります。 この場合、ユーザーはパスワードを管理者として再入力する必要があります。 この問題を回避するには、資格情報に SSO を使用します。