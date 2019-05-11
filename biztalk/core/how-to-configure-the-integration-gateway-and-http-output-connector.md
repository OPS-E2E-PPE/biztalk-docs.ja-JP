---
title: 統合ゲートウェイと HTTP 出力コネクタを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Integration Gateway
- gateway nodes, creating
- HTTP Output Connector
ms.assetid: a02ee533-07a8-42fa-a72a-7e5359b18f40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b054893004f270ca352dc537c60ef8fcb719cba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340832"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a>統合ゲートウェイと HTTP 出力コネクタを構成する方法
統合ゲートウェイと HTTP 出力コネクタを構成するこれらの手順に従います。  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>作成して新しいゲートウェイ ノードを構成するには  
  
1.  Web ブラウザーでは、PeopleSoft アプリケーションを開きます。  
  
2.  検索**PeopleTools**、 **Integration Broker**、し、**ゲートウェイ**。  
  
3.  **検索によって**フィールドに「 `LOCAL`、 をクリックし、**検索**します。  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  入力`machine-name/PSIGW/PeopleSoftListeningConnector`に、**ゲートウェイ URL**エントリ。  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  をクリックして**更新**、 をクリックし、**保存**します。  
  
6.  をクリックして、**プロパティ**リンク**HTTPTARGET**をその ID のプロパティと値の組み合わせを表示するには  
  
     ここでは、またはノード定義には、URL を設定することができます。 ここでは、ノード レベルで、URL を設定します。  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a>参照  
 [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)