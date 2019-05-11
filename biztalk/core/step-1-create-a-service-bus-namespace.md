---
title: 手順 1:Service Bus の Namespace を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d8986f729d48fd25066bd166749d6bfb2b7ed3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392829"
---
# <a name="step-1-create-a-service-bus-namespace"></a>手順 1:Service Bus の Namespace を作成します。
この手順で作成、 [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]名前空間。 この名前空間を使用して、Salesforce から営業案件通知を受信するためのリレー エンドポイントがホストされます。 後でこのソリューションを作成するには、処理中に使用するこのリレー エンドポイントに通知メッセージが表示される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a>作成する、[!INCLUDE[sb](../includes/sb-md.md)]名前空間  
  
1.  ログオン[ http://manage.windowsazure.com ](http://manage.windowsazure.com) Microsoft アカウントを使用します。  
  
2.  ページの下部には、次のようにクリックします。**新規**、 **App Services**、 **Service Bus Relay**、し**簡易作成**です。  
  
3.  名前空間を入力します。 `BtsSalesforce` 、現在の所在地に最も近いリージョンを選択します。 クリックして**リレーの作成**です。  
  
    > [!CAUTION]
    >  この名前空間はグローバルに一意である必要があります。 そのため、このチュートリアルで説明されている 1 つ以外の名前空間を使用する必要があります。  
  
    > [!NOTE]
    >  リレーは、操作の一部として作成されません、名前空間はことに注意してください。 受信場所を構成するときに、このチュートリアルの後半でリレー エンドポイントを作成、 **Sb-messaging**アダプター。  
  
4.  設定されて、名前空間が作成されると、 **Active**します。 状態がアクティブにするとは、名前空間を選択およびクリックして**アクセス キー**に接続する方法の詳細を取得するには、ページの下部にある、 **BtsSalesforce** の値を含む、名前空間**既定のユーザー**と**既定のキー**します。 これらの詳細は、このチュートリアルで後ほど必要があります。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 6:BizTalk Server 2013 を Salesforce と統合します。](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)