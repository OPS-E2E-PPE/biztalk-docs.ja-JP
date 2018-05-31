---
title: HTTP ノードをテストする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2790a4e3fa0ff1ed9a9b9b0c2018108c9cbb1282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255530"
---
# <a name="how-to-test-the-http-node"></a>HTTP ノードをテストする方法
HTTP ノードをテストするには、次の手順を実行します。  
  
### <a name="to-test-the-http-node"></a>HTTP ノードをテストするには  
  
1.  PeopleSoft Enterprise でに移動**PeopleTools**、 **Integration Broker**、**モニター**、 **Monitor Message**です。  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  クリックして、**ノードの状態**タブです。  
  
3.  **Message Node Name**フィールドに「 `MSEXTERNAL`、[] をクリックし、、**ルックアップ**アイコン。  
  
4.  **Message Node Name** **MSEXTERNAL**です。  
  
     PeopleSoft が HTTP 経由で通信していることを示すメッセージが表示されます。  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     メッセージが表示されない場合は、次のことを確認します。  
  
    1.  IP アドレスおよびポートが、受信ポートおよびノードと一致していること。  
  
    2.  BizTalk Server が実行されていること。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft HTTP ホストおよびポートを作成します。](../core/creating-a-peoplesoft-http-host-and-port.md)