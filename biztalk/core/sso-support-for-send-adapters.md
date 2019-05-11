---
title: 送信アダプターの SSO のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efe1b6eac59478dea5e7ba56351c543c04f8c223
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398960"
---
# <a name="sso-support-for-send-adapters"></a>送信アダプター用の SSO サポート
エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカル、ネットワーク、およびドメインの境界を格納および転送するサービスを提供します。 トランスポート アダプターを作成する場合は、トランスポート アダプターがバックエンド アプリケーションへのアクセスに使用するユーザーの資格情報を処理するために SSO Api を利用できます。  
  
 SSO をサポートしないトランスポート アダプターは、通常、バックエンド アプリケーションにアクセスするために使用する資格情報の 1 つのセットで構成される必要です。 多くのバックエンド システムでは、1 つのアカウントの認証がすべてのセキュリティの実施を満たしていません。 多くのアプリケーションでは、それらにアクセスしているユーザーに応じて異なるアクセス権を提供します。 SSO により、アダプターを動的にアクセスしようとしたユーザーに基づくエンドポイントに使用する資格情報を選択します。  
  
## <a name="how-send-adapters-work-with-sso"></a>アダプターと SSO の連携を送信する方法  
 送信の SSO をサポートするアダプターを検証し、チケットを引き換えるし、を使用して、SSO システムからユーザーの資格情報を取得、 **ISSOTicket.ValidateAndRedeemTicket** API。 アダプターは、送信先エンドポイントに対する認証を取得した資格情報を使用します。  
  
 次のコード フラグメントでは、送信アダプターが SSO システムからユーザーの資格情報を取得する方法を示しています。  
  
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
 パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ識別子 (SID) を対応する構成済みの BizTalk Server パーティにマップします。 この情報が使用できるようにするアダプター設定の 2 つのシステム メッセージ コンテキスト プロパティでは、必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決で使用するにはコンポーネントは構成されている場合。  
  
 **WindowsUser** redmond\myBtsUser など、送信者のドメイン ユーザーとプロパティが設定されます。 **SignatureCertificate**クライアント認証証明書の拇印を持つプロパティが設定されます。  
  
## <a name="managing-passwords"></a>パスワードの管理  
 エンドポイントのプロパティに直接資格情報を配置する場合、パスワード フィールドが空になります、バインド ファイルをエクスポートする必要がある場合。 管理者としてパスワードを再入力をユーザーが必要になります。 SSO 資格情報を使用すると、この問題を回避できます。