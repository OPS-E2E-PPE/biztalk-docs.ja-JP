---
title: HTTP ノードをテストする方法 |Microsoft Docs
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
ms.openlocfilehash: 27e3ebdc1c75ba0e42e5af8a57e194d3ab363753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333881"
---
# <a name="how-to-test-the-http-node"></a>HTTP ノードをテストする方法
HTTP ノードをテストする次の手順に従います。  
  
### <a name="to-test-the-http-node"></a>HTTP ノードをテストするには  
  
1.  PeopleSoft Enterprise に移動します。 **PeopleTools**、 **Integration Broker**、**モニター**、**メッセージの監視**します。  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  をクリックして、**ノードの状態**タブ。  
  
3.  **Message Node Name**フィールドに、入力`MSEXTERNAL`、 をクリックし、**ルックアップ**アイコン。  
  
4.  **Message Node Name**、 **MSEXTERNAL**します。  
  
     メッセージが表示され、PeopleSoft が HTTP 経由で通信することを示します。  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     メッセージを受け取らない場合は、次のことを確認します。  
  
    1.  IP アドレスとポート、受信ポートと、ノードの間と一致します。  
  
    2.  BizTalk Server が実行されています。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)