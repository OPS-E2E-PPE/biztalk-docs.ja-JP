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
ms.openlocfilehash: edfd57afb1eba520c6ae0211cbb6bc0e90922d59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398975"
---
# <a name="sso-support-for-receive-adapters"></a>受信アダプターの SSO のサポート
エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカル、ネットワーク、およびドメインの境界を格納および転送するサービスを提供します。 トランスポート アダプター ライターは、トランスポート アダプターがバックエンド アプリケーションへのアクセスに使用するユーザーの資格情報を処理するために SSO Api を活用できます。  
  
 SSO をサポートしないトランスポート アダプターは、通常、バックエンド アプリケーションにアクセスするために使用する資格情報の 1 つのセットで構成される必要です。 多くのバックエンド システムでは、1 つのアカウントの認証がすべてのセキュリティの実施を満たしていません。 多くのアプリケーションでは、それらにアクセスしているユーザーに応じて異なるアクセス権を提供します。 SSO により、アダプターを動的にアクセスしようとしたユーザーに基づくエンドポイントに使用する資格情報を選択します。  
  
## <a name="how-receive-adapters-work-with-sso"></a>アダプターと SSO の連携を受け取る方法  
 受信アダプターがメッセージを受け取った後、BizTalk Server に発行する前に、SSO のサポートが次の手順を実行します。  
  
1. アダプターが、送信側を偽装しを使用して送信者の代わりに SSO チケットを取得、 **ISSOTicket.IssueTicket** API。  
  
2. SSO チケットを正常に取得した後、アダプターは、それをメッセージ コンテキスト プロパティ"SSOTicket"システム名前空間の下で格納します。  
  
   次のコード フラグメントは、チケットを取得する方法と、メッセージ コンテキストに格納する方法を示します。  
  
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
 パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ識別子 (SID) を対応する構成済みの BizTalk Server パーティにマップします。 この情報が使用できるようにするアダプター設定の 2 つのシステム メッセージ コンテキスト プロパティでは、必要があります**WindowsUser**と**SignatureCertificate**、下流のパーティの解決で使用するにはコンポーネントは構成されている場合。  
  
 **WindowsUser** redmond\myBtsUser など、送信者のドメイン ユーザーとプロパティが設定されます。 **SignatureCertificate**クライアント認証証明書の拇印を持つプロパティが設定されます。  
  
## <a name="managing-passwords"></a>パスワードの管理  
 エンドポイントのプロパティに直接資格情報を配置する場合、パスワード フィールドが空になります、バインド ファイルをエクスポートする必要がある場合。 管理者としてパスワードを再入力をユーザーが必要になります。 SSO 資格情報を使用すると、この問題を回避できます。  
  
 アダプターのエンドポイントがある場合、**パスワード**プロパティ、実際の値がクリア テキストで、SSO 構成ストア データベースに格納されていることに注意してください。 これは、ファクトとしてユーザー インターフェイスに表示されることに関係なく、"*"。 このプロパティはネットワークを介して転送もと、BizTalk Server サンプルの ExplorerOM を使用して単純なスクリプトが読み取ることになります。