---
title: 受信アダプターの SSO サポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4767387c-f24b-4986-aaed-6724c5d6b347
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00948d53ada9dd5eb428b0d1975e16b21b19064d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008435"
---
# <a name="sso-support-for-receive-adapters"></a>受信アダプターの SSO のサポート
エンタープライズ シングル サインオン (SSO) には、ローカル、ネットワーク、およびドメインの境界間で暗号化されたユーザーの資格情報を格納および転送するサービスが用意されています。 トランスポート アダプター ライターは SSO API を利用して、トランスポート アダプターがバックエンドのアプリケーションにアクセスするために使用するユーザー資格情報を処理できます。  
  
 SSO をサポートしないトランスポート アダプターは、通常、バックエンド アプリケーションにアクセスするために使用する資格情報の 1 つのセットで構成される必要です。 多くのバックエンド システムの場合、単一のアカウント認証ではすべてのセキュリティの実施に対応できません。 多くのアプリケーションは、それらのアプリケーションにアクセスしているユーザーに応じて異なるアクセス権を提供します。 アダプターは、SSO を使用して、アクセスしようとしているユーザーに基づいてエンドポイントに使用する資格情報を動的に選択できます。  
  
## <a name="how-receive-adapters-work-with-sso"></a>受信アダプターと SSO の連携  
 SSO をサポートする受信アダプターは、メッセージを受け取った後、および BizTalk Server にそのメッセージを公開する前に次の手順を実行します。  
  
1. アダプターが、送信側を偽装しを使用して送信者の代わりに SSO チケットを取得、 **ISSOTicket.IssueTicket** API。  
  
2. SSO チケットが取得できたら、アダプターはシステム名前空間の下のメッセージ コンテキスト プロパティ "SSOTicket" にその SSO チケットを保存します。  
  
   次のコードは、チケットの取得方法と、メッセージ コンテキストへのチケットの保存方法を示しています。  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                         IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_SSOToken = null;  
  
 // Get a ticket for the sender  
     private void GetSSOTicket(IntPtr token)  
     {  
       bool impersonated = false;  
      WindowsImpersonationContext wic = null;  
  
 if (token != (IntPtr)0)   
 {  
     try   
 {  
         // Impersonate the user using his security  
 // token  
            WindowsIdentity wi =   
 new WindowsIdentity(token);  
            wic = wi.Impersonate();  
            impersonated = true;  
  
         // Get an SSO ticket for the impersonated  
 // user  
            ISSOTicket ssoTicket = new ISSOTicket();  
            m_SSOToken = ssoTicket.IssueTicket(0);  
         }  
         finally   
 {  
           if (impersonated)  
            // Revert the impersonation  
            wic.Undo();  
          }  
}  
}  
...  
  
     private void WriteSSOTicketToContext(  
 IBaseMessage message )  
     {  
         if (m_SSOTicket != null)   
 {  
 // Write the SSO ticket to the message context  
          message.Context.Write(  
 “SSOTicket”,  
 http://schemas.microsoft.com/BizTalk/2003/system-properties,   
 m_SSOToken);  
        }  
      }  
}  
```  
  
## <a name="party-resolution"></a>パーティの解決  
 パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ ID (SID) を、対応する構成済み BizTalk Server パーティにマップします。 この情報が使用できるようにするアダプター設定の 2 つのシステム メッセージ コンテキスト プロパティでは、必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決で使用するにはコンポーネントは構成されている場合。  
  
 **WindowsUser** redmond\myBtsUser など、送信者のドメイン ユーザーとプロパティが設定されます。 **SignatureCertificate**クライアント認証証明書の拇印を持つプロパティが設定されます。  
  
## <a name="managing-passwords"></a>パスワードの管理  
 エンドポイントのプロパティに直接資格情報を設定する場合、バインド ファイルをエクスポートする必要があるときはパスワード フィールドが空になります。 この場合、ユーザーはパスワードを管理者として再入力する必要があります。 この問題を回避するには、資格情報に SSO を使用します。  
  
 アダプターのエンドポイントがある場合、**パスワード**プロパティ、実際の値がクリア テキストで、SSO 構成ストア データベースに格納されていることに注意してください。 実際には、パスワードはユーザー インターフェイスに "*" として表示されます。 また、このプロパティはネットワークを介して転送され、BizTalk Server のサンプルの ExplorerOM を使用する単純なスクリプトでこのプロパティを読み取ることができます。