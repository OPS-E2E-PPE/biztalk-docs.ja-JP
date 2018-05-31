---
title: 統合ゲートウェイと HTTP 出力コネクタを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: acfa52be85a664432af95af0ca292e9cc394c6ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247922"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a>統合ゲートウェイと HTTP 出力コネクタを構成する方法
統合ゲートウェイと HTTP 出力コネクタを構成するには、次の手順を実行します。  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>新しいゲートウェイ ノードを作成および構成するには  
  
1.  Web ブラウザーで、PeopleSoft アプリケーションを開きます。  
  
2.  検索**PeopleTools** **Integration Broker**、し、**ゲートウェイ**です。  
  
3.  **検索によって**フィールドに「 `LOCAL`、クリックしてして**検索**です。  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  入力`machine-name/PSIGW/PeopleSoftListeningConnector`に、**ゲートウェイ URL**エントリです。  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  をクリックして**更新**、クリックして**保存**です。  
  
6.  クリックして、**プロパティ**リンク**HTTPTARGET**をその ID のプロパティ/値の組み合わせを表示するには  
  
     URL をここか、またはノード定義に設定できます。 ここでの説明では、URL をノード レベルに設定します。  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a>参照  
 [PeopleSoft HTTP ホストおよびポートを作成します。](../core/creating-a-peoplesoft-http-host-and-port.md)