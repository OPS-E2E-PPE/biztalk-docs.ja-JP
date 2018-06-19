---
title: 受信アダプターの SSO サポート |Microsoft ドキュメント
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
ms.openlocfilehash: 8e3c992f47ad46b4a9d5ee095ad650f6cc492179
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22276666"
---
# <a name="sso-support-for-receive-adapters"></a>受信アダプターの SSO のサポート
エンタープライズ シングル サインオン (SSO) には、ローカル、ネットワーク、およびドメインの境界間で暗号化されたユーザーの資格情報を格納および転送するサービスが用意されています。 トランスポート アダプター ライターは SSO API を利用して、トランスポート アダプターがバックエンドのアプリケーションにアクセスするために使用するユーザー資格情報を処理できます。  
  
 SSO をサポートしないトランスポート アダプターでは、一連のバックエンド アプリケーションにアクセスするために使用する資格情報で構成されている通常必要です。 多くのバックエンド システムの場合、単一のアカウント認証ではすべてのセキュリティの実施に対応できません。 多くのアプリケーションは、それらのアプリケーションにアクセスしているユーザーに応じて異なるアクセス権を提供します。 アダプターは、SSO を使用して、アクセスしようとしているユーザーに基づいてエンドポイントに使用する資格情報を動的に選択できます。  
  
## <a name="how-receive-adapters-work-with-sso"></a>受信アダプターと SSO の連携  
 SSO をサポートする受信アダプターは、メッセージを受け取った後、および BizTalk Server にそのメッセージを公開する前に次の手順を実行します。  
  
1.  アダプターが送信元を偽装しを使用して、送信者の代わりに SSO チケットを取得、 **ISSOTicket.IssueTicket** API です。  
  
2.  SSO チケットが取得できたら、アダプターはシステム名前空間の下のメッセージ コンテキスト プロパティ "SSOTicket" にその SSO チケットを保存します。  
  
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
 パーティの解決パイプライン コンポーネントは、送信者の証明書または送信者のセキュリティ ID (SID) を、対応する構成済み BizTalk Server パーティにマップします。 この情報が使用できるようにするアダプターでも、2 つのシステム メッセージをコンテキスト プロパティ設定する必要があります **WindowsUser** と **SignatureCertificate**, 、構成されている場合は、下流のパーティの解決コンポーネントが消費できるようにします。  
  
 **WindowsUser** redmond\myBtsUser たとえば、送信者のドメイン ユーザーを伴うプロパティが設定されます。 **SignatureCertificate** クライアント認証証明書の拇印を持つプロパティが設定されます。  
  
## <a name="managing-passwords"></a>パスワードの管理  
 エンドポイントのプロパティに直接資格情報を設定する場合、バインド ファイルをエクスポートする必要があるときはパスワード フィールドが空になります。 この場合、ユーザーはパスワードを管理者として再入力する必要があります。 この問題を回避するには、資格情報に SSO を使用します。  
  
 アダプターのエンドポイントがある場合、 **パスワード** プロパティには、実際の値をクリア テキストで SSO 構成ストア データベースに保存することに注意してください。 実際には、パスワードはユーザー インターフェイスに "*" として表示されます。 また、このプロパティはネットワークを介して転送され、BizTalk Server のサンプルの ExplorerOM を使用する単純なスクリプトでこのプロパティを読み取ることができます。