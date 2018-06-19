---
title: '手順 1: サービス バスの Namespace を作成する |Microsoft ドキュメント'
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
ms.openlocfilehash: f4d7630316f72fd63bac5ce7127b5451683e2f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276762"
---
# <a name="step-1-create-a-service-bus-namespace"></a>手順 1: サービス バスの Namespace を作成します。
この手順で作成、 [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]名前空間。 この名前空間を使用して、Salesforce からの営業案件通知を受信するリレー エンドポイントをホストします。 このソリューションを作成するプロセスの後半で、このリレー エンドポイントを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムで通知メッセージを受信します。  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a>[!INCLUDE[sb](../includes/sb-md.md)] 名前空間を作成するには  
  
1.  ログオン[http://manage.windowsazure.com](http://manage.windowsazure.com) Microsoft アカウントを使用します。  
  
2.  ページの下部で、をクリックして**新規**、 **App Services**、 **Service Bus リレー**、し**簡易作成**です。  
  
3.  名前空間を入力`BtsSalesforce`し、現在の地理的な場所に最も近い地域を選択します。 をクリックして**リレーの作成**です。  
  
    > [!CAUTION]
    >  この名前空間はグローバルで一意である必要があります。 したがって、このチュートリアルで使用している以外の名前空間を使用する必要があります。  
  
    > [!NOTE]
    >  この操作で作成されるのは名前空間だけであり、リレーは作成されませんのでご注意ください。 受信場所を構成するとき、このチュートリアルで後ほど、リレー エンドポイントが作成された、 **Sb-messaging**アダプター。  
  
4.  状態が に設定されている名前空間の作成後、 **Active**です。 名前空間を選択し、をクリックできますステータスがアクティブ、**アクセス キー**に接続する方法の詳細を取得するには、ページの下部にある、 **BtsSalesforce** の値を含む、名前空間**既定のユーザー**と**既定のキー**です。 これらの詳細は、チュートリアルの後半で必要になります。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 6: Salesforce との BizTalk Server 2013 の統合](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)