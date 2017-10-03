---
title: "手順 1: アプリケーション プール Id の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, application pools
- application pools
ms.assetid: 66286327-8580-4378-89ee-ddd7204b03c6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61ee2994e81c3fdd352506d6a9757cde557fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-application-pool-identity"></a>手順 1: アプリケーション プール Id を構成します。
このチュートリアルでのアプリケーション プールを使用する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Web サービスとして公開するオーケストレーションを処理するように、インターネット インフォメーション サービス (IIS)。 アプリケーション プールは、ワーカー プロセスで処理された 1 つまたは複数の Url のグループです。  
  
 アプリケーション プールの id は、アプリケーション プールのワーカー プロセスを実行するサービス アカウントの名前です。 既定では、アプリケーション プールは、低レベルのユーザー アクセス権があり、このチュートリアルでは関数には十分ではありませんが、ネットワーク サービスのユーザー アカウントで動作します。 セキュリティ上の理由では、絶対最小権限を持つユーザー アカウントにアプリケーション プール id を構成するメッセージ ボックス データベース (BizTalkMsgBoxDb) および (とも呼ばれる、BizTalk の構成データベースに書き込む最小のアクセス許可管理データベース、または BizTalkMgmtDb)。  
  
### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a>アプリケーション プールを実行するサービス アカウントを変更するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  インターネット インフォメーション サービス (IIS) マネージャーでは、ローカル コンピューター を展開し、展開**アプリケーション プール**です。  
  
3.  構成するアプリケーション プールを右クリックし (既定では、このチュートリアルの実行、 **DefaultAppPool**)、順にクリック**プロパティ**です。  
  
4.  DefaultAppPool プロパティ ダイアログ ボックスで、 **Identity**  タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**定義済み**|選択を解除**定義済みの**します。 **定義済みの**次などの標準的なサービス アカウントを参照します。<br /><br /> -   **ネットワーク サービス**(既定)、リモート コンピューター上のリソースにアクセスするために使用できる低レベルのユーザー アクセス権を持っています。<br />-   **ローカル サービス**、低レベルのアクセス権を持っています。 リモート コンピューター上のリソースへのアクセスを必要としない場合は、この設定を使用します。<br />-   **ローカル システム**、Network Service や Local Service アカウントよりも多くのユーザー権限を持つアカウントであります。|  
    |**構成可能**|選択**構成可能な**します。 **構成可能な**は登録されているユーザー名を参照します。|  
    |**ユーザー名**|ワーカー プロセスを操作するアカウントのユーザー名を入力します。|  
    |**Password**|パスワードを入力します。|  
  
5.  **[OK]**をクリックします。  
  
    > [!NOTE]
    >  代わりに、セキュリティ強化のため、このチュートリアルに対応したアクセス許可で作成したカスタム id を実行しているまったく新しいアプリケーション プールを作成できます。  
  
 進みます[手順 2: 新しいプロジェクトを作成](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)